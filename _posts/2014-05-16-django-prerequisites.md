---
layout: seminar
title: Setting up Django
author: David Naftalin
---
####Install [pip](http://pip.readthedocs.org/en/latest/installing.html)

pip is the python installer package and allows you to install and manage python packages really easily. 

Once downloaded the three most useful commands are:

    pip install <package> 
    pip install -u <package>  # upgrades any existing packages 	
    pip freeze                # list all packages currently available on your computer

####Install virtualenvwrapper & virtualenvwrapper
    
virtualenv is a tool that allows you to create and manage different environments for different projects. It basically means that if you need to install lots of different packages for different projects, you can make separate directories in which to install them and work from. This prevents you developing huge swathes of installed packages in your global environment and not being able to remember which ones are needed for each project.
    
virtualenvwrapper is just something someone has built around virtualenv that provides a bunch of shortcuts for virtualenv.

    pip install virtualenv
    pip install virtualenvwrapper
    export WORKON_HOME=~/Envs
    mkdir -p $WORKON_HOME$ 
    source /usr/local/bin/virtualenvwrapper.sh
    mkvirtualenv env1
    
Now we have to write lines 3 and 5 in your terminal’s start up files so we don’t have to write all these commands every time we want to use virtualenvwrapper (assuming that you are using the nano test editor):
    	
    nano ~/.bash_profile  

Copy and paste lines 3 & 5 
Ctrl-x to exit (you will be prompted to save)

Now lets create a directory called ‘envs’ in which to keep our virtual environments and then create our first virtual environment.

    mkdir ~/envs
    ls envs	  
    mkvirtualenv django-blog

You should notice now that at the beginning of each line in your terminal there is the name of your environment in brackets:

    (django-blog)$

This means you are now in your virtual environment. Lets see what’s installed:

    pip freeze

You should get:

    >>>wsgiref==0.1.2

This is automatically installed when you create a new virtualenv

Let's download django:
	
    pip install django
    pip freeze	

    >>>wsgiref==0.1.2	
    >>>django==1.6.4

Now let's install a couple tools that are so useful in web-development

    pip install ipython  

IPython is a  great python shell that allows you to write across lines and also gives helpful information on lots of commands.       

    pip install ipdb 

*ipdb* is the most useful thing in the world. If you’ve used the python visualiser, its  basically that but for the program your actually writing. I’ll show you.

    pip freeze
    >>>wsgiref==0.1.2     
    >>>django==1.6.4
    >>>ipdb==0.8
    >>>ipython==1.2.1

Let's leave the virtualenv:

    deactivate
	
Try pip freeze again and you’ll see that nothing you downloaded is there. If you want to get back into your virtual environment just type:

    workon django-blog  

You use these commands anywhere on your computer rather than   going to the envs directory itself (that's basically what virtualenvwrapper did).

Maybe we can see why this is useful now. If you have one project in which you are using Django 1.4 and one in which you are using 1.6, its pretty handy for them to only exist in certain environments. It gets pretty confusing otherwise and things might clash and stop working.

Remember that if your code is dependent on certain packages, it will only work if you have activated the environment in which you have downloaded those packages. Always remember to work from the environment that you’ve created for each project.

