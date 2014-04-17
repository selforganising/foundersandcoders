---
layout: seminar
title: Decomposing a problem using recursion
---
Following on from [finding the factorial of a number](/2014/04/01/factorial.html), here is the same problem solved in Python using recursion.

#### Find the factorial of a number

The mathematical definition of `n!` can be given as:

    n! = n x (n-1)!  where n > 1
    n! = 1           where n = 0

This is a *recursive* definition with a *base case*. 

The *recursive* definition defines factorial in terms of itself. This definition can be applied several times *recursively* to get the answer.

The definition also includes a *base case*, which tells you when to stop. This base case is crucial. Without it the recursive definition would repeat endlessly. 

Here is an example:

    4! = 4 x 3!             apply the recursive definition
    4! = 4 x 3 x 2!         apply the recursive definition again
    4! = 4 x 3 x 2 x 1!     apply the recursive definition again
    4! = 4 x 3 x 2 x 1 x 0! apply the recursive definition again
    4! = 4 x 3 x 2 x 1 x 1  apply the base case
    4! = 24

So, a recursive function is always defined in terms of itself and some base case where the final value is returned.

Let's do this in Python.

#### Give the function a sensible name

    factorial

#### Work out the inputs to the function and give them sensible names

    n

#### Write out the first line of the function definition, including the arguments

    def factorial(n):

#### Decide on the _base case_

    n == 0

#### Add a test for the _base case_

    print factorial(0) == 1

#### Add a return value for your function using the value that your test is expecting

    def factorial(n):
        if n == 0:
            return 1

    print factorial(0) == 1

#### Run your test and check that it passes

    True

#### Decide on the next case

    n == 1

In the case of a function like `factorial`, which computes a number that is part of a sequence, it is easy to decide on the each successive test case. In this case, the next value is _n! = 1_, where `n == 1`.

#### Add another test using the next case

    print factorial(1) == 1

#### Decide on whether you are ready to compute a recursive solution

Sometimes more than one base case is required before the general recursive solution can be found. But in this case the problem is a simple one: 

_For any value of n, multiply n by each predecessor until you reach the base case._

#### Sketch out the framework of a possible solution

A general recursive solution often requires that:

    some function of n

is combined with:

    some operator

to a recursive call to the original function with

    some successor to n

This schema will not work in every case, but is a sensible starting point.

This is the heart of recursive programming. You are calling a function _within the function itself_. That is, you are calling it _recursively_.

This is a very important and powerful technique in programming.

#### Attempt to fill in the blanks

This is where the big intuitive leap is required. 

    n! = n * (n-1) * (n-2) * ... * 3 * 2 * 1

From the form of the solution to n!, probably the first thing to see clearly is that:

    some operator of n = *

The second thing to see is that:

    some function of n = n

This comes from the first term in the series.

The final thing to see is that:

    some successor to n = n - 1

Which should be clear from the way in which each term of n! is one less than its predecessor.

#### Now attempt a general solution to the problem

    def factorial(n):
        if n == 0:
            return 1
        return n            *     factorial(n - 1)
               ^            ^                 ^
         function of n   operator       successor to n   


#### Add more test cases

    print factorial(0) == 1
    print factorial(1) == 1
    print factorial(2) == 2
    print factorial(3) == 6
    print factorial(4) == 24

#### Run the tests

    True
    True
    True
    True
    True

Which confirm that this is probably a good general solution.

