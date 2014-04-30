---
layout: seminar
title: Regular expressions and webapp2 routes
---
A *webapp2.WSGIApplication* object that invokes the *MainPage* handler when any request is made might look like this:

    app = webapp2.WSGIApplication([('.*', MainPage)])

One that runs when a path consists of nothing but digits might look like this:

    app = webapp2.WSGIApplication([('/[0-9]+', PostPage)])

And here is one that sends those digits as an argument to the *PostPage* handler:

    app = webapp2.WSGIApplication([('/([0-9]+)', PostPage)])

In each of these examples, a single route is expressed as tuple where the first element of the tuple is a *regular expression* that represents the path to be matched to the incoming URL request.

Here they are again:

    .*           Any string
    [0-9]+       One or more occurences of the digits 0 to 9
    ([0-9]+)     ...and capture those digits for later use

Here are some more:

    .             Any character
    .?            0 or 1 occurence of any character
    a?            0 or 1 occurence of the character 'a'
    [a-z]         Any lowercase character
    [^a-z]        Any character that is not lowercase
    [a-z]+        One or more occurrences of any lowercase character
    [a-zA-Z0-9]   Any alphanumeric character
    \w            The same as [a-zA-Z0-9_]
    \s            Any whitespace character (a space, a tab or a newline)
    \d            The same as [0-9]
    \d+           One or more digits       
    \d{4}         Exactly four digits
    [\w-]         Any alphanumeric character or an underscore or a hyphen
    (   )         Capture whatever is in parentheses for later use

If you use more than one set of parentheses in a route then the captured expressions are passed in order as arguments to the handler.

    app = webapp2.WSGIApplication([( '/posts/(\d{4})/(\d{2})/(\d{2})' , PostPage )])

Which matches a path like:

    /posts/2014/04/30

And sends *'2014'*, *'04'* and *'30'* in order as arguments to the *PostPage* handler.



