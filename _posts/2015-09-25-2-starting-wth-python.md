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
Since Mac is a operating system that is derived from Unix most of the things we talk about in this course will also work on a mac (Try opening a terminal and do some of the things you learned in the last lecture). Sadly Apple did not implement a package manager (outside the walled garden that is the AppStore), butluckily there is a community alternative called [Homebrew](http://brew.sh/). If you want more information take a look at [this tutorial](http://dghubble.com/blog/posts/homebrew-os-x-package-management/).

## Compiling packages from source.
If a software is not available with a package manager you are probably going to have to install that package from source.

- Explain
  - source code
  - compiling
  - binaries
  - Every installation is different search for a file called readme/install

# What is Python

- Introduce
  - REPL
  - IPython
  - Running scripts

## Resources on Python

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

# Homework
The homework is due on *October 1 2015* at *7:30am*.

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
