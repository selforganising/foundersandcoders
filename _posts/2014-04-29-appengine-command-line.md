---
layout: seminar
title: App Engine and the command line
---
You can connect to Google App Engine using the App Engine Launcher, but you may find it easier to use the command line. You can use your own computer or a Nitrous account.

Here are a few commands that you might find helpful while working through CS253.

####Run a simple web server to view the contents of your current working directory

    python -m SimpleHTTPServer 3000

Run the server on port 3000. The `-m` option searches `sys.path` for the named module and runs the corresponding `.py` file as a script.

This will not help with App Engine applications, but is useful for viewing static HTML files.

####Clone a repository into your current working directory

    git clone https://github.com/GoogleCloudPlatform/appengine-helloworld-python.git

In this case, it is the App Engine Hello World app in Python.

####Run an App Engine application on this server

    dev_appserver.py --host=0.0.0.0 --port=3000 <path-to-directory>

####Deploy an application to App Engine

    appcfg.py update <path-to-directory>

####Check that you can reach a remote URL

    ping udacity-cs253.appspot.com

`Ctrl-c` to terminate.

####Fetch a file at a remote URL

    curl -O http://udacity-cs253.appspot.com/static/hw2.tgz

In this case, it is the answer to CS253 Homework 2. The `-O` option copies the contents into a local file with the same name as the original.

####Unzip the contents of an archive file

    tar -xvf hw2.tgz

`x` extract, `v` verbose, `f` extract to a file.

####A quick way to write debugging information to the command line

At the top of your application file:

    import logging

And then at any point in your code:

    logging.info("<any string here>")

This will then write output to the command line when *dev_appserver.py* is running.

