---
layout: post
title: 2. Starting with Python
categories: []
tags:
  - news
published: false
---

# Installing Software under Linux
Linux/Unix based system use package managers to install and update software packages.

Under Ubuntu the package manager is called `apt` and uses `*.deb` files as packages.

- `apt-get` is the central command for updating and installing software.
  - `apt-get install *pkgname*` Installs the package with name *pkgname*
  - `apt-get update` Updates the local cache of available packages.
  - `apt-get upgrade` Upgrades all installed packages to the newest available version.
- `apt-cache search *searterm*` searches the local cache of available packages after *searchterm*

Some of these commands change system files and since Linux/unix has a very strict security mindset you will have to prefix them with `sudo`(*s*witch *u*ser *do* `cmd`).
For more information that a look at [this tutorial by Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-manage-packages-in-ubuntu-and-debian-with-apt-get-apt-cache) or [the ubuntu help](https://help.ubuntu.com/community/AptGet/Howto).

### Note: If you are using Mac OSX
Since Mac is a operating system that is derived from Unix most of the things we talk about in this course will also work on a mac (Try opening a terminal and do some of the things you learned in the last lecture). Sadly Apple did not implement a package manager (outside the walled garden that is the AppStore), but luckily there is a community alternative called [Homebrew](http://brew.sh/). If you want more information take a look at [this tutorial](http://dghubble.com/blog/posts/homebrew-os-x-package-management/).

## Compiling packages from source.
If a software is not available with a package manager you are probably going to have to install that package from source. The source code is a human readable description of the program. Just to name a few `C`, `Fortran`, `C++`, `C#`, `Java`, `Matlab`, `Perl`, `Haskell`, `Python`, `Julia`, `R` and `JavaScript`. All these languages differ a bit, sometimes they follow fundamentally different principles or have different target audiences, but one of the broadest possible differences is at which point in time the translation from source code to machine code is happening. For languages that are more low-level (closer to the metal) the translation from source code to machine code (a process that is called compiling) happens before the execution. The output the compiler creates is called a binary. Python on the other hand is a interpreted or *J*ust *i*n *T*ime compiled (JIT'ed) language, that means that the translation into a machine understandable representation happens as late as possible, this gives a create deal of flexibility and enables many of the high-level features of python.

```sh
# Example of an installation from source
wget http://www.greenwoodsoftware.com/less/less-458.tar.gz # wget downloads files from remote hosts
tar -xvf less-458.tar.gz # tar.gz is the zip format of Linux
cd less-458
./configure
make
# Test the program
dmesg | ./less # use the freshly build binary
# Sine we already have less installed on our system we don't need to do this
# make install
```

There are a lot of different tool-chains and ways of actually compiling packages, so before you start doing it take a look at the programs `INSTALL` or `README` description.

For more information on `./configure && make && make install` [take a look here](https://robots.thoughtbot.com/the-magic-behind-configure-make-make-install)

# Other resources
The scientific computing section at OIST is maintaining a set of documentations at [SCS](https://groups.oist.jp/scs/documentation) and for all things Linux I can always recommend the [ArchLinux wiki](https://wiki.archlinux.org/).

# What is Python

- Introduce
  - REPL
  - IPython
  - Running scripts

## Resources on Python

- Python documentation
- Good basic tutorial

# Control structures

## If statements

## For loops

## While loops

# Functions
In Python we can wrap independent pieces of code in *functions*. We then can call these functions from the REPL or from other functions. A function should always only do one thing and that one thing well (and you should always check your input).
In Python a function is defined by `def *function_name*(arguments...):` and the `return` keyword specifies what it gives you back.

```python
def square(x):
  return x*x # Calculate the square of x

def sum_squared(x, y):
  return square(x) + square(y)

def say(name):
  print("Hello ", name, " how are you doing today?")

def square_list(list)
  """ Takes a list of numbers and squares them"""
  return map(square, list)

print(square(2.0))
say("Sascha")
print(square_list([1,2,3,4,5]))
```

You should always document your function with line comments `#` (try to make them more useful than my example above eg. don't state the obvious.) and describe what your function does with a [docstring](https://www.python.org/dev/peps/pep-0257/) (see the `square_list` example).

- Links about function scopes
- Keyword arguments

# Data structures and memory

## Atomic Data Types

### Booleans

### Numbers

### Characters

## Built-in collections

### Lists and arrays

### Strings

### Dictionaries

## Classes

## Binary search trees
A very useful data structure is the *binary search tree*

# Homework
The homework is due on *October 1 2015* at *12:00pm* (eg. noon).

1. Install `python 2.7` and the `ipython-notebook` on your virtual machine(VM).
2. Update the software that is installed on your VM.
1. What is a function? Describe in your own words.
2. What is a class? Describe in your own words.
3. Transform the following for loop into an equivalent while loop.
4. What are atomic data-structures and why are they special?
5. What is a list? In other programming languages you might encounter the term array, is there any difference to a list in python?
6. Implement a binary search tree in python (assume that element types are integers). This task is fairly challenging, so don't worry if you don't succeed and just hand in how far you got and why you got stuck there.
7. How would you test that your implementation is correct?
8. What might the be the benefits of a tree as opposed to a list. Think about searching and sorting entries. (No worries if you don't know what to write down here. We are going to talk about this in two weeks in more detail.)
