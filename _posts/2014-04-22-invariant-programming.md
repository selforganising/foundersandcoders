---
layout: seminar
title: Invariant programming
---
After looking at [*Decomposing a problem using recursion*](/2014/04/17/recursion.html), we have not finished with recursion and we have not finished with the factorial function either.

Here is a solution to the factorial function again:

    def factorial(n):
        if n == 0: 
            return 1
        return n * factorial(n - 1)

There is a different solution that keeps track of the accumulated calculation and adds this accumulated total as an argument to the function, like this:

    def factorial(n, acc=1):
        if n == 0:
            return acc
        return factorial(n - 1, n * acc)

Looking at the last line of this function, it is just a recursive call to the function with new argument values. Unlike the earlier version, no other calculations are done after each recursive call is returned. 

And the base case no longer returns just the result of the base case (i.e. `0! = 1`), but returns the accumulated value passed to it.

This function therefore has two interesting properties. 

First, the recursive call on the last line is the last operation performed inside the function. This is unlike the previous version, where the result of the function call has to be multiplied by *n* before returning a result. This property has a name: *tail recursion*.

And second, it uses an *accumulator* that keeps track of the intermediate result of each successive calculation.

These two features together--tail recursion with an accumulated result--are an exampe of *invariant programming*.

With invariant programming, each recursive call uses both intermediate inputs and intermediate outputs, as the inputs are call-by-call turned into outputs.

The program does not need to keep track of each recursive call and do a final calculation (in this case, multiplication by *n*) before returning a result.

Tail recursive calls do not require a *call stack*, if the compiler is capable of doing *tail call optimisation*. Languages like Python, Java and almost all widely-used languages cannot do tail call optimisation and using recursive functions even if they are tail recursive will eventually lead to a stack overflow.

Here is what the call stack for the original definition looks like for factorial(5):

    5 * factorial(5-1)
    5 * 4 * factorial(4-1)
    5 * 4 * 3 * factorial(3-1)
    5 * 4 * 3 * 2 * factorial(2-1)
    5 * 4 * 3 * 2 * 1 * factorial(1-1)
    5 * 4 * 3 * 2 * 1 * 1

And here is the invariant stack:

    factorial(5)
    factorial(5 - 1, 5 * 1 )
    factorial(4 - 1, 4 * 5 )
    factorial(3 - 1, 3 * 20 )
    factorial(2 - 1, 2 * 60 )
    factorial(1 - 1, 1 * 120 )
    120

With a tail-recursive compiler, there would be no stack explosion in the invariant version.

For a clear exposition of invariant programming, see Peter Van Roy's excellent [Paradigms of Computer Programming](https://www.edx.org/course/louvainx/louvainx-louv1-01x-paradigms-computer-1203).
