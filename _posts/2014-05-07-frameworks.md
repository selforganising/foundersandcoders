---
layout: seminar
title: Using CSS frameworks
---

####Task: style your blog using a frontend framework

#####Before we start

Follow the [code school course on Chrome DevTools](http://discover-devtools.codeschool.com/), Chapters 1 and 2.

Once you start doing fontend programming, you are going to want to spend a lot of time tweaking CSS and JavaScript in your browser. This course is an excellent introduction.

If you want a refresher on HTML and CSS, spend a bit of time with the [Codecademy web track](http://www.codecademy.com/tracks/web).

#####Working in groups

This task is well-suited to a division of labour. The research tasks can be split up between several people and the application of one or other framework to a website is a significant piece of work that can easily be shared, even if each website ends up looking different.

#####What is a frontend framework?

A CSS framework will generally consist of a stylesheet with an array of pre-defined classes that can be included in an HTML page to determine elements of layout, typography, forms, buttons and navigation. Full frontend frameworks like Foundation and Bootstrap also contain JavaScript libraries and icons to add further elements of design and behaviour.

Although it takes a lot of time and patience to get really familiar with these frameworks, it is possible to get some familiarity quite quickly.

#####Why Foundation and Bootstrap?

Bootstrap is the most widely-used frontend framework. Foundation is preferred by some. Between them, They are the two most popular frameworks in use today.

#####How to use them?

The frameworks can be downloaded straight from their respective websites, but the standard downloads contain a lot of files that you will not necessarily need.

It has in recent years become standard practice not to download CSS and JavaScript library files, but to link to them in HTML pages using third-party CDNs (Content Delivery Networks), for example [cdnjs.com](http://cdnjs.com/).

It is increasingly the case that web pages are constructed with styling, scripts, images and data all provided from different sources.

Any additional site-specific styling or behaviour can be added in separate _.css_ or _.js_ files that you create and edit yourself.

#####Sample pages

* [Bootstrap](/resources/bootstrap.html)
* [Foundation](/resources/foundation.html)

Download them and look at the course code.

Use Chrome's Developer tools ( _"Inspect element"_ in the context menu) to investigate the relationship between a document's HTML and the CSS.

Pay particular attention to the headers and to the `row` and `columns` _divs_ in Foundation and the `row` and `col-md-4` _divs_ in Bootstrap.

In _foundation.html_, what is the significance of `foundation.min.css`, `modernizr.min.css`, `jquery.min.js` and `foundation.min.js`?

In _bootstrap.html_, what is the significance of `bootstrap.min.css`, `bootstrap-theme.min.css`, `jquery-1.10.2.min.js` and `bootstrap.min.js`.

Where are these files being served from? Does their location on the page matter? What is a *protocol-relative path* and why would you want to use one?

#####Take a look at the online docs

* [Bootstrap](http://getbootstrap.com/css/)
* [Foundation](http://foundation.zurb.com/docs/components/grid.html)

Pay particular attention to the way grids are laid out. Ignore anything that you do not understand after the second or third reading. A lot of the details are really not necessary to get the gist of how these frameworks work.

#####Edit the source code

Save and play with the [Bootstrap](/resources/bootstrap.html) and [Foundation](/resources/foundation.html) files and get a feel for how they work.

#####Follow an example on CodePen

[This 5-step example](http://codepen.io/sofer/pen/BHuer) uses Foundation. Try creating your own empty files and copying the code step-by-step. This will give you some idea of the process of building up the look-and-feel of a page.

#####Decide which framework you prefer

You may want to try a Google search for e.g. _foundation vs bootstrap_.

#####Finally, style your blog using one of the two frameworks

#####For the end-of-day review:

* Which framework did you prefer and why?
* How does your blog now look?

