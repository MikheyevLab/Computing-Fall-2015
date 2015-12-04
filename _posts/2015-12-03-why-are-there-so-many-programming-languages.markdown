---
layout: post
title: "Why are there so many programming languages?"
date: "2015-12-03"
---

![](http://xrds.acm.org/images/4833512699_761a3fcc61_b.jpg)

I found the [best and shortest answer on Reddit](https://www.reddit.com/r/explainlikeimfive/comments/1jk4jo/eli5_why_are_there_so_many_programming_languages/):

"Same reason why you have a fork, a knife and a spoon. Some things are better for some tasks then others.
Not only that, but people who are very good with computers sometimes think, "I bet I can make something that is even better then a knife at slicing cheese!" and comes up with a cheese slicer. Then another person thinks: "I like the fork, knife and spoon, but they take up too much space." So they invent the spork.

So there are a lot of languages that have their own specialization. So it's better to write scientific programs in R and web applications in Javascript."

## What are the most popular languages?

![](https://qzprod.files.wordpress.com/2015/04/the-most-used-programming-languages-on-stack-overflow-2013-2014-2015_chartbuilder-1.png?w=640)

## Languages are about trade-offs

![](http://i.stack.imgur.com/OB8ZS.png)

## Why so many languages?

### Some are easier to learn

- C++

```c++
#include <iostream.h>

int main()
{
    std::cout << "Hello, world!\n";
}
```

- Javascript

```JavaScript
<TITLE>
Hello World in JavaScript
</TITLE>
<SCRIPT>
    document.write ("Hello, world!")
</SCRIPT>
```
- Python

```python
print("Hello world!")
```

### Languages are modified to make them 'better' in some way

- E.g., Python3 made functions more consistent
```
print "Hello, World!"
```
vs.
```
print("Hello, World!")
```

- Functionality is added over time, and new languages are born.
- 'Better' is inherently subjective and fierce debates ensue.
  - Some languages (e.g., [Julia](http://julialang.org/)) try to make this objective by, say, saying they are faster.
  - Still [debates continue](https://matloff.wordpress.com/2014/05/21/r-beats-python-r-beats-julia-anyone-else-wanna-challenge-r/).

### Abstraction
- High-level languages aim to have large reusable chunks
- New languages can have additional levels of abstraction.
  - E.g., C++ introduced more support for object-oriented programming and generic programming over C. Initially, C was a subset of C++, but they have increasingly diverged over time.

### New Infrastructure
- What computers can do is greatly influenced by the technological capabilities of the time.
- This usually means new levels of abstraction to help deal with the hardware
   - E.g., new assembly language to deal with move from 16 bit to 32 bit processors
   - [node.js](https://nodejs.org/en/), which is a scaleable framework for handling many concurrent web connections
- For scientific computing, we have to deal with connections to databases and HPC

### Culture
- Most of the time you will be either re-using code or looking up solutions online.
- The path of least resistance for solving a particular problem.
- We use R not because it is a particularly elegant or high performance language, but because of its many useful scientific libraries.

## What does this mean for you?
- On a daily basis, I use these languages: R, Python, SQL, awk, bash. Why?
- You can actually call functions in other languages using bridges.
  - E.g., you can [call R directly from python](https://sites.google.com/site/aslugsguidetopython/data-analysis/pandas/calling-r-from-python)
  - A typical bash script or snamake workflow can call all sorts of stuff.

## Links

Let us Google that for you:

- [Why Does The World Need More Programming Languages?](http://www.fastcolabs.com/3031443/why-does-the-world-need-more-programming-languages)
- [O'Reilly poster](http://cdn.oreillystatic.com/news/graphics/prog_lang_poster.pdf)
- [More ways to write a "Hello, World!" program](http://www2.latech.edu/~acm/HelloWorld.shtml)
