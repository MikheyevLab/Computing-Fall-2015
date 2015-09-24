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
Python is a general-use, high-level programming language. It aims to provide a simple syntax combined with a powerful base library, to enable a high productivity and accessibility for programmers. [Take a look at this blurb](https://www.python.org/doc/essays/blurb/).

Running Python on the terminal will provide you with a `REPL` interface. Similar to the output shown below.

```
Python 3.4.3 (default, Sep  7 2015, 15:40:35)
[GCC 5.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

`REPL` stands for *r*ead-*e*valuate-*p*rint *l*oop and it allows you to enter Python code directly into the terminal and see the result of the computation.

```
>>> 1+2
3
>>> print("Hello World!")
Hello World!
>>>
```

## Running scripts
Often you want to save a series of Python commands as a script. For that you can open a text file in an editor. Write the commands you want to be executed and then save the file with a `.py` ending. Execute the file then from the command line with `python myfile.py`.

### Editors
> On the terminal you can use `nano`, `vim` or `emacs` to open and write text files. `nano` is the simplest of the three and the other two are very powerful, but also have a steep learning curve.
> Otherwise we recommend using a graphical text editor with syntax highlighting for Python like `Atom` or `Sublime Text`.

## Jupyter/IPython

## Resources on Python
There are many good resources on the web on how to use python. As first point of contact use the [official documentation](https://docs.python.org/3/) and [Dive into Python3](http://www.diveintopython3.net/) as well as [How to think as a computer scientist](http://openbookproject.net/thinkcs/python/english2e/)(However this is in Python2).

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

## Function scopes

You can define functions and variables within different contexts in Python (and most other languages). Some definitions are *globabl*., i.e., available throughout the code, while others are *local*, and are defined within particular contexts. In general, it is better to use local variables, and understand how scoping works, so as to minimize potential for variable names conflicting.
- [A Beginner’s Guide to Python’s Namespaces, Scope Resolution, and the LEGB Rule](http://spartanideas.msu.edu/2014/05/12/a-beginners-guide-to-pythons-namespaces-scope-resolution-and-the-legb-rule/)
- [StackOverflow discussion on Python function scopes](http://stackoverflow.com/questions/291978/short-description-of-python-scoping-rules)

## Function arguments

You can pass variables to functions, including variable length argument Lists:
- [Very basic intro](http://www.ibiblio.org/g2swap/byteofpython/read/keyword-arguments.html)
- [How to use \*args and \*\*kwargs in Python](http://www.saltycrane.com/blog/2008/01/how-to-use-args-and-kwargs-in-python/). More advanced

# Data structures and memory

Python has many data types. Each has its particular properties and uses. There is a good overview of data types in [Dive Into Python](http://www.diveintopython3.net/native-datatypes.html). Among those you should know are:

- [Atomic Data Types:](http://www.diveintopython3.net/native-datatypes.html) these are used to store low-level data
 - Booleans
 - Numbers
 - Characters
- Built-in collections: used to create relationships between data
 - Lists and arrays
 - Strings
 - Dictionaries
- [Classes & Iterators](http://www.diveintopython3.net/iterators.html) Classes are used to model the world and to define objects that can be used to store data and to operate upon.

    ```python
    class Person:
        def __init__(self, name, age):
            self.name = name
            self.age = age
        def say(self):
          print("Hello ", self.name, " how are you doing today?")

    ta = Person("Valentin", 23)
    ta.say()
    ```
    Iterators on the other hand are a very handy concept to work efficiently with large sets of data.

## Binary search trees
A very useful data structure is the *binary search tree*. A tree consists of a directed acyclic graph in which every node has `n` children. A graph is a set of nodes (think cities on a map) that are connected by edges (think roads between cities). In a directed graph you can only travel along one a edge in one direction (think water pipes). Acyclic just means that there are no loops in the graph. Below you can see a generic tree (turn it upside down to see why it is called a tree ;) ).

```
   A
 / | \
C  D  E
|    / \
F   G   H
```

A binary search tree is a tree where each node only has *two* children and there is a order relationship between the *root* and its children.

```
    A
   / \
  B   C
 / \   \
D   E   F
```

The left child of the root is always smaller than the root and the right child is always larger (under a defined ordering operator). Such a tree is always completely sorted and the smallest element in the tree is the left-most element and the biggest element is the right-most element.

# Homework
The homework is due on *October 1 2015* at *12:00pm* (eg. noon). Hand in your homework either as a IPython notebook or a pdf + the source code you wrote.

1. Install `python 3.4 or 3.5` and `jupyter` or the `ipython-notebook` on your virtual machine(VM).
2. Update the software that is installed on your VM.
1. What is a function? Describe in your own words.
2. What is a class? Describe in your own words.
3. Transform the following for loop into an equivalent while loop.

    ```python
    for i in range(1, 10):
        if i % 2 == 0:
            print(i)
    ```
4. What are atomic data-structures and why are they special?
5. What is a list? In other programming languages you might encounter the term array, is there any difference to a list in python?
6. What is a dictionary? How do you check if a key is already present? Hw do you get a list of keys and/or a list of values?
7. What is the difference between a list and an iterator? In python take a look at `range` versus `xrange`.
9. Let's say you want to read a very large file that contains many lines of text. What is the advantage of using an iterator, compared to a list when looping over all of its lines?
6. Implement a binary search tree in python.
  - First think about how you would model such a tree and what basic components it has.
  - Assume that element types are integers.
  - Implement the search tree in a class.
  - Implement a function that inserts an integer into the tree.
  - Implement a function that creates a tree from a list of integers.
  - Implement a function that takes a tree and an integer and searches for the integer in the tree. Returning `true` if it is in the tree and `false` if not.
  - Implement a function that prints a tree from its smallest to it largest element.
  - *Note:* This exercise is fairly challenging, so don't worry if you don't succeed and just hand in how far you got and why you got stuck there.
7. How would you test that your implementation is correct?
8. What might the be the benefits of a tree as opposed to a list. Think about searching and sorting entries. (We are going to talk about this in two weeks in more detail.)

