---
layout: seminar
title: Object-oriented programming in Python
---
A ***class*** is a block of code that defines ***data*** and ***behaviour***. 

An ***object*** is ***instantiated*** from  a class. It contains its own data and behaviour, as defined by the class.

The advantage of ***encapsulating*** data and behaviour in this way is that it allows the programmer to effectively model complex real-world behaviour. In practical terms, it can help keep a program organised into manageable parts that do not become impossibly hard to maintain as an application grows in size. 

In Python, a class is defined as follows:

    class Thing(object):
        pass

`class` announces a new class definition, just as `def` announces a function definition. Note the capitalisation of *Thing*. In Python, this is a convention that you should take care to stick to.

Classes exist in a ***class heirarchy***, where ***subclasses*** that define more specific behaviour are descended from ***superclasses*** that define more general behaviour. In Python all classes ***inherit*** from the `object` class, which is so general it cannot be used at all, except through sublclassing. In other words, it is an ***abstract class***.

An object is instantiated like this:

    whatsit = Thing()

In a program, it is the objects that are created and manipulated to get meaningful output and the classes that define what those objects can contain and what they can do.

The behaviour of an object is defined in its ***methods***. Methods are just functions that are available to objects of a class. 

    class Thing(object):
       
        def communicate(self):
            print "Hello, I am a thing."

    whatsit = Thing()
    whatsit.communicate()

    >>> Hello, I am a thing

In Python, every method of a class must be defined with an object of that class as its first argument. This is a quirk of the implementation of methods in Python. By convention, the argument name used is ***self***. 

When an object ***calls*** one of its methods, the object itself is inserted as the first argument of the method. In this way, the definition of a method has one more argument than when the method is called.

    whatsit.communicate()

and

    Thing.communicate(whatsit)

Are equivalent.

When an object is instantiated, it is normal to do so with arguments. These arguments are passed to a ***constructor***. A constructor is a method that is called when an object is first created. In Python, this method is called ***`__init__`*** (a so-called *magic method* in Python, of which there are several).

    class Thing(object):

        def __init__(self, colour):
            self.colour = colour

        def communicate(self):
            print "Hello, I am " + self.colour

    whatsit = Thing('blue')
    whatsit.communicate()

    >>> Hello, I am blue

The data of an object are generally known as ***attributes***, which are just variables that are defined in the object. In this case, the *whatsit* object has an attribute of *colour*, as defined in the Thing class, with value *'blue'*. 

Objects can be ***composed*** of attributes that are themselves objects. In this way, methods can be called from objects within objects:

    whatsit.surface.set_texture('smooth')

When an object calls one of its  methods, if the method is not defined in the class from which that object derives, then the superclasses are scrutinised for a method with the appropriate name.

Classes can inherit their behaviour from more than one superclass but, in general, this is not recommended practice. Classes defined with more than one superclass can often lead to confusion. 
