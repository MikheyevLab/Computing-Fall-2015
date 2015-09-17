---
layout: post
title: 1. Welcome to Computing
categories: []
tags:
  - news
published: true
---

# Resources

## Installing a Linux Virtual Machine (VM)
If you have Linux running on your laptop you don't need to follow this step. You are already a pro. Otherwise follow [these instructions](http://www.wikihow.com/Install-Ubuntu-on-VirtualBox). They are for Windows, but should work similarly on the Mac.

You can then make your way to the [command line](https://help.ubuntu.com/community/UsingTheTerminal), where the real fun begins.

## Navigating the command line
Here are a number of useful links:
- This [tutorial from the University of Surrey](http://www.ee.surrey.ac.uk/Teaching/Unix/) is a good introduction. Read up to chapter 4, and leave the rest for later.
- [An Introduction to Linux Virtual Workshop](https://cvw.cac.cornell.edu/Linux/default). This tutorial is slightly more advanced, and has a good introduction to file permissions and redirection.

### More advanced tutorials
These might be overkill to start with, but we list them here as references you may want to check out later.
- [LinuxCommand.org](http://linuxcommand.org/lc3_learning_the_shell.php). Very comprehensive into, though perhaps a bit dense.
- [A Practical Guide to Linux Commands Editors and Shell Programming]([http://www.aem.umn.edu/~aem3100/spring2013/Prentice_Hall_A_Practical_Guide_to_Linux_Commands_Editors_and_Shell_Programming_2nd.pdf](http://www.aem.umn.edu/~aem3100/spring2013/Prentice_Hall_A_Practical_Guide_to_Linux_Commands_Editors_and_Shell_Programming_2nd.pdf)
- ). This is an actual book, covering a lot of different topics.
- [Shell workshop](http://www.pehjota.net/guides/shell-workshop/) A series of slides and code examples for how to use the shell. Perhaps a bit dry, but very useful.
- [Basic Linux Navigation and File Management](https://www.digitalocean.com/community/tutorials/basic-linux-navigation-and-file-management). More general and basic intro.
- [Linux Driver's Ed](http://www.physics.smu.edu/coan/linux/index.html) **Goal:** To transform an intelligent, motivated person with zero linux experience into a capable linux user without inducing tears, drawing blood or triggering frustration-fueled outbursts of profanity.

## Install python
There are Ubuntu-specific instructions provided in [this form answer](http://askubuntu.com/questions/244544/how-do-i-install-python-3-3). You will get a lot of your most useful information from forum answers like this one. Follow these instructions up to `make && sudo make install`

You can then use `pip`, which comes with Python to [install IPython](http://ipython.org/install.html), an interactive environment you can use for playing around (`pip install "ipython[notebook]"`). You can then play around with the awesome [ipython notebook computational environment](http://ipython.org/notebook.html). We also have a [public server](http://ipython.oist.jp:8888). Don't keep any files on the public server though, it will periodically be purged.

# Homework
1. These are exercises to be finished by next week's class. Please submit homework to Valentin as a pdf, using proper English, and proper formatting of code blocks. You are encouraged to write your responses in [Markdown](http://daringfireball.net/projects/markdown/syntax) a mini-language that allows for easy conversion of plain text to HTML with proper code highlighting. It is super-useful (the content of this site is written in Markdown). For writing in Markdown (and also for general programming) we recommend the excellent [Atom](https://atom.io) editor, which has installable packages that can convert Markdown to a variety of other formats, such such pdf (_e.g._, markdown-pdf, which is installable via Preferences -> Install). Of course, there are numerous other tools.
  - These are the most important linux commands you should know for sure. Describe what each one does in your own words
  - `ls`
  - `cd`
  - `mkdir`
  - `cp`
  - `rm`
  - `ln`
  - `cat`
  - `man`
  - `less`

1. Which shortcuts refer to (a) the current directory (b) to the directory above the current one (c) the home folder?
1. What is the difference between a folder and a directory?
2. How do you remove an empty directory? What if it is not empty? Give examples.
3. How would you find out more about a command? (List three options)
4. What are links? How might they be useful?
5. How would you differentiate a directory from an ordinary file on the command line. How about a link?
6. Create two directories (let's call them A and B). Go into A and create a (soft-)link to B. Go into that link. Where are you know? Go back to the original directory and delete B. What happend to the link in A?
7. Can you describe the difference between a hard-link and a soft-link? Compare your result from 8. with creating a hard-link to a normal file and deleting the original.
8. Execute the command `dmesg`. How would you see only the last 50 lines. How about the first 50 lines? How would you save the output as a file? How would you search the output for a keyword? Since the command is creating a lot of output is there a way to read the output at your own pace?
9. Why do you think using the command line might be useful? What surprised you?
10. What are pipes and how are they useful? Give a couple of examples using the commands in Question 1.
11. Let's say you are working in one directory in your filesystem (_e.g._, `/usr/local/dir1/dir2/xyzdir345`), then switch to another one (`cd /usr/local/foo`). Now you want to go back to the previous directory, but don't want to type out the full path name. How can you do it quickly?
