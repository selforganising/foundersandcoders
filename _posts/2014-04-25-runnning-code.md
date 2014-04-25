---
layout: seminar
title: "Running code from the Unix command line"
---

Open a terminal window of login to your Nitrous account.

####Get the CS101 code from GitHub

    git clone git@github.com:udacity/cs101.git

####Install any Python modules you need

    pip install --user beautifulsoup4

In this case, it's [Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/).

`--user` is needed when you do not have full access rights to read and write files, as is the case on Nitrous. 

If you are on a Mac, you can also try:

    sudo pip install beautifulsoup4

`sudo` = *SuperUser DO*. Install something outside the current user's home directory on a part of the file system that would not normally be editable by them. 

####Run the code

Try working on Udacity exercises in an editor and running them via the command line:

    python studentMain.py

