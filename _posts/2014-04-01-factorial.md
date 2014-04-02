---
layout: slideshow
title: "A simple solution: finding the factorial of a number"
---

## Whatever it is that you are trying to do, think of it as a function and give it a sensible name {: #1}

    factorial

`factorial` is a pretty sensible name for a function that returns the factorial of a number :-)

[Next](#2){: .button .round .next}

## Work out the inputs to the function and give them sensible names. {: #2}

    n

In general, descriptive names are better, but in the case of an integer, certain letters like `i`, `j`, `k` and `n` are so universally used to denote integers as to be quite descriptive enough. In this case, it should be clear that `factorial` takes a single whole number.

[Next](#3){: .button .round .next}

## Write out the first line of the function definition, including the arguments.{: #3}

    def factorial(n):
        pass

The `pass` operation does nothing, but ensures that your code will run without errors (even if it gives the wrong answer).

Add a test using the most simple argument values that you can think of.

    print factorial(0) == 1

There are many ways to do testing in Python. This is a good start.

[Next](#4){: .button .round .next}

## Add a return value for your function using the value that your test is expecting.{: #4}

    def factorial(n):
        return 1

    print factorial(0) == 1

Run your test and check that it passes.

    True

[Next](#5){: .button .round .next}

## Think of a sensible name for your return value, add a variable with that name at the top of your function, assign to it your return value and return the variable instead of the value {: #5}

    def factorial(n):
        total = 1
        return total

    print factorial(0) == 1

Assuming that we know that a factorial produces the product of a number and all the positive integers that precede it, then `total` is not a bad name for the return value. `product` might be a reasonable choice, too.

[Next](#6){: .button .round .next}

## Run your test again and check that it passes.{: #6}

    True

[Next](#7){: .button .round .next}

## Add another test using the next most simple argument values that you can think of. {: #7}

    print factorial(1) == 1

If necessary, extend your function definition, so that both your tests pass.

    def factorial(n):
        total = 1
        return total

    print factorial(0) == 1
    print factorial(1) == 1

[Next](#8){: .button .round .next}

##In this case, it is not necessary to add any code. {: #8}

    True
    True

## Add another test using the next most simple argument values that you can think of.

    print factorial(2) == 2

[Next](#9){: .button .round .next}

## Extend your function definition, so that all your tests pass.{: #9}

    def factorial(n):
        total = 1
        if n > 1:
            total = n
        return total

    print factorial(1) == 1
    print factorial(1) == 1
    print factorial(2) == 2

There are other ways to attack this problem, and this is not yet a good general solution, but the tests will pass.

[Next](#10){: .button .round .next}

## Add yet another test using the next most simple argument values that you can think of.{: #10}

    print factorial(3) == 6

[Next](#11){: .button .round .next}

## Extend your function definition, so that all your tests pass.{: #11}

This is one possible approach:

    def factorial(n):
        total = 1
        if n > 1:
            total = n
        if n > 2:
            total = n * n - 1
        return total

    print factorial(1) == 1
    print factorial(1) == 1
    print factorial(2) == 2
    print factorial(3) == 6

But, at this point (and quite possibly earlier) anyone who is familiar enough with `while` loops will see that this approach is not going to generalise very well and will probably suspect that there is a better way to do it.

[Next](#12){: .button .round .next}

## Like this:{: #12}

    def factorial(n):
        total = 1
        while n > 1:
            total = total * n
            n = n - 1
        return total

    print factorial(1) == 1
    print factorial(1) == 1
    print factorial(2) == 2
    print factorial(3) == 6

This, in fact, is a perfectly reasonable answer. All the tests will pass.

And further tests will confirm that this is a good general solution.

Now, there is no easy way to make the cognitive leap required to recognise that this solution requires a looping structure of the kind illustrated, but the purpose of this slow and deliberate approach is to get to the point where you have a suitable framework in which to think about possible solutions.

At least if you can get to the point where you have the skeleton of a solution and some passing tests, you can concentrate on working out the core of a problem without the baggage of an ill-defined function with misconceived arguments and spurious return values.

