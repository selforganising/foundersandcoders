---
title: List Comprehensions
layout: seminar
---

The manipulation of lists is at the heart of a lot of programming problems.

### A list of squares

    def listofsquares(alist):
        squares = []
        for i in alist:
            squares.append(i * i)
        return squares

&nbsp;

    >>> listofsquares([1, 2, 3, 4])
    [1, 4, 9, 16]
    
### A list of squares using a list comprehension

List comprehensions introduce a terse style for manipulating lists. 

    def listofsquares(alist):
        return [ i * i for i in alist ]

&nbsp;
 
    >>> listofsquares([1, 2, 3, 4])
    [1, 4, 9, 16]

  

### A list of even squares

    def listofevensquares(alist):
        return [ i * i for i in alist if i % 2 == 0]
 
&nbsp;
 
    >>> listofevensquares([1, 2, 3, 4])
    [4, 16]
    
If you are interested in learning more about list comprehensions, Udacity's *Design of Computer Programs* has a [nice introduction](https://www.udacity.com/course/viewer#!/c-cs212/l-48703331/m-48728207). You may also want to look at the [Python documentation](https://docs.python.org/2/tutorial/datastructures.html#list-comprehensions) or [Python for Beginners](http://www.pythonforbeginners.com/lists/list-comprehensions-in-python/).
