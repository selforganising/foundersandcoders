---
layout: seminar
title: Jinja templates
---

Following on from [yesterday's seminar](http://foundersandcoders.org/2014/05/01/jinja.html), where we had a *render* method like this:

    def render(self, template, **kw):

We might call *render* from within the `get` or `post` method of a *handler* like this: 

    self.render('blog_front.html', posts=oposts)

The `posts=oposts` argument is of this form because it is being passed into the `**kw` argument of the *render* method, which takes any number of *key=value* pairs (in this case just one). And let us assume that the `oposts` variable contains a list of previously-collected *post* objects.

The *blog_front* template might look like this:

    { % extends "base.html" %}
    {% block title %}Blog posts{% endblock %}
    { % block content %}
      <ul>
      { % for post in posts %}
        <li><a href="/posts/{ { post.id }}">{ { post.title }}</a></li>
      { % endfor %}
      </ul>
    { % endblock %}

And a bare-bones *base* template might look like this:

    <!DOCTYPE html>
    <html>
      <head>
        <title>{ % block title %}The site{ % endblock %}</title>
      </head>
      <body>
        { % block content %}
        { % endblock %}
      </body>
    </html>

The `{\% block %}` tags indicate a block of text that may be over-ridden by a template that extends the base template and extends or replaces the block.

The *blog_front* template might also have something that looks like this:

    { { post.render() }} 

Which will work if each *post* is an object that has a *render* method, defined somewhere in your application. This could be used, for example, to turn carriage returns into \<br\> tags.

It could also have something like this:

    { { post.render() | safe }}

Where the `|` denotes a custom filter in which the function (and it can be any regular Python function) is on the right and first argument to the function is on the left, so that this is equivalent to inserting into the document:

    safe(post.render())

Which, in this case, will ensure that the post is appropriately escaped.

You could also do something like:

    { { post.date | datetimeformat('%d-%m-%Y') } }}

Which will format a date nicely.

There is more (much more) to [Jinja](http://jinja.pocoo.org/) and [Jinja templating](http://jinja.pocoo.org/docs/templates/), but this should be enough to get you going.