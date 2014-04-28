---
layout: seminar
title: Filter, map and reduce
---

We now have [a couple of levels active on Memrise](http://www.memrise.com/course/275461/python-programming-language/).

The Lists level includes three very powerful and useful functions that we have not yet covered: `filter`, `map` and `reduce`.

####filter

    def f(x): return x % 2 != 0  # return True if odd

    filter(f, [1,2,3])
    >>> [1, 3]

or

    filter(lambda x: x % 2 != 0, [1,2,3])


####map

    def f(x): return x*x*x       # return the cube

    map(cube, [1,2,3])
    >>> [1, 8, 27]

or

    map(lambda x: x*x*x, [1,2,3])

###reduce

    def f(x,y): return x+y       # add two numbers together

    reduce(add, [1,2,3])
    >>> 6

or

    reduce(lambda x,y: x+y, [1,2,3])


`lambda` just means *this is a function without a name that takes the following arguments*.

Now go and [give Memrise a spin](http://www.memrise.com/course/275461/python-programming-language/).
