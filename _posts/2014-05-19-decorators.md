---
layout: seminar
title: Decorators in Python
---
A decorator is a pretty simple idea. It is a function that modifies another function.

Or in the case of `@classmethod` it is a function that modifies a whole class.

It is analogous to taking any value, transforming it in some way and returning a new value.

    def square(i):
        return i**2
    x = square(x)

No big deal. We have just changed the value of *x* from some integer to the square of that integer. This is basic programming in Python.

But what if the value we are taking is not an integer but a function:

    def logger(f):
        def with_log(*args, **kwargs):
	    print "Arguments: %s, %s" % (args, kwargs)
	    return f(*args, **kwargs)
        return with_log

    f = logger(f)

In this case, we are taking some function *f* and printing out some logging information before returning the function.

None of the work is done until *f* is actually called. When it is, the arguments used are passed to the *with_log* function defined in *logger*. This prints out some logging information before returning the original function.

Using the decorator syntax, instead of writing:

    def f():
        <define f here>
    f = logger(f)

we can write:

    @logger
    def f():
        <define f here>

It is a simple difference, but having the decorator directly above the function definition aids readability. It is just syntactic sugar.

In the case of a class method:

    @classmethod
    def by_id(cls, uid):
       return User.get_by_id(uid)

is equivalent to:

    def by_id(cls, uid):
        return User.get_by_id(uid)
    by_id = classmethod(by_id)

It is an easy way to announce that a method is intended not to act on a single instance of a class, but instead on the whole class.

It is nothing particularly clever. It is just telling the reader, *"watch out, this is a class method"*.

That's it.

If you want more information, Bruce Eckel has written a good [Introduction to Python Decorators](http://www.artima.com/weblogs/viewpost.jsp?thread=240808).


