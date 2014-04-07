---
layout: seminar
title: A quick introduction to the UNIX command line
---

####Before we start

You may want to set up a remote development environment (particulary if you are not running OS X or Linux).

Sign up for [Nitrous.IO](https://www.nitrous.io/join/e_9dsA7hhRE?utm_source=nitrous.io&utm_medium=copypaste&utm_campaign=referral), have a quick read through the [Getting Started](http://help.nitrous.io/categories/getting-started/) guide and set up a Python/Django box. You can then login and open up a console window.

Or, if you prefer, just open a terminal window on your computer.

####Additional learning resources

After you have worked through the quick summary below, you can take a look at [The Command Line Crash Course](http://cli.learncodethehardway.org/book/).

And to get the commands into your head, have a go at [this course on Memrise](http://www.memrise.com/course/159960/command-line-the-hard-way-linuxosx/).

####A quick step-by-step summary of the basics

#####Where am I?

    pwd

_"Print Working Directory"_

#####What's in my current directory?

    ls

_"LiSt"_

#####Show me hidden files, as well

    ls -a

#####And show me details of each file

    ls -l

#####Show me both details and hidden files

    ls -al

#####Make a new directory called _things_

    mkdir things

_"MaKe DIRectory"_

#####Change to the _things_ directory

    cd things

_"Change Directory"_

#####Go up a directory level

    cd ..

#####Return to my home directory

    cd ~

#####Create a new file with nothing in it

    touch one.txt

`touch` changes the access and modification time of a file (i.e. it _touches_ it), but this also creates a new file if none exists with the name given.

#####Make a copy of it

    cp one.txt two.txt

_"CoPy"_

#####Change its name

    mv one.txt three.txt

_"MoVe"_

#####And delete  it

    rm three.txt

_"ReMove"_

#####Remove all files and folders without prompting and with no chance of recovery

    rm -rf .

_"ReMove Recursively and Forcefully"_ everything in your current working directory. Don't do this. Instead, `mkdir ~/tmp` and `mv` anything you no longer want to there.

#####Remove a directory

    rmdir things

_"ReMove DIRectory"_ (you need to empty it first)

#####Put some text into a file

    echo "hello" > greet.txt

#####And display the contents

    cat greet.txt

_"conCATenate and list"_

#####Complete the name of a file without having to type it all

    touch afilewithalongname
    cat af<tab>

(i.e. use the `tab` key)

#####Create a file within a folder within a folder

    mkdir one
    mkdir one/two
    echo "hello" > one/two/three.txt

#####Read its contents

    cat o<tab><tab><tab>

(i.e. use the `tab` key three times in succession)

#####Cycle through previously-entered commands

Use the up and down arrow keys

#####Edit a previously-entered command

Use the left and right arrow keys

#####Run some python code

    echo "print 'hello world'" > hello.py
    python hello.py

#####Enter the Python shell

    python

#####Leave it again

    Ctrl-d

or 

    exit()

#####Install the beautifulsoup4 Python module

    pip install beautifulsoup4

Or, if your user account does not have full access rights to read and write files:

    pip install --user beautifulsoup4

