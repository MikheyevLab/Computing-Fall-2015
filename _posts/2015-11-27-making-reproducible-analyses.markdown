---
layout: post
title: "Making reproducible analyses"
date: "2015-11-27"
---

# Why bother?

- A fundamental tenet of programming is that you want to be lazy. If you solved a problem once, your solution should be re-usable for other similar situations. It saves you time
- Science is meant to be reproducible. Very often there is not enough detail in a paper to repeat the analysis. Don't be like those people.

## What do to?

You want to try writing code that is easy to read, re-use and share. Ideally, you want a system that forces you to do all of these things as part of you general workflow, or you will be tempted to cheat as a form of expediency. There has been an increasing interest in making pipelines reproducible for bioinformatics. For a long time there has been a GUI tool called [Galaxy](https://galaxyproject.org) that allows you to chain programs together. While easy to use, it is not flexible. Recently, there have been several other tools that do similar things, but with more customizability. One tool that I like is [Snakemake](https://bitbucket.org/johanneskoester/snakemake/wiki/Home). It has an active user community and is under active development. It is written in Python3, and uses it to do all of its work. However, there are other tools, like the recently published [BigDataScript](http://pcingola.github.io/BigDataScript/bigDataScript_manual.html), which has its own language. They are not only for bioinformatics, but can be used for any heavy data analysis.

Today we'll focus on snakemake.

## Installing snakemake

Snakemake is written in python3 and is already installed on Tombo, and can be loaded using `module load python/3.5.0`

If you wish to install it on your computer, you ca do it using pip:

```
pip install snakemake
```

## Getting the lesson

This lesson is forked from

```
https://github.com/mikheyev/SandwichesWithSnakemake.git
```

## Homework
1. Write a rule that takes the output of `peanut_butter_and_jelly_sandwich_recipe` in `basic.snake` and transforms it into another file.
2. For each file in `./exercises/manyFiles` find the sum of the squares of the numbers inside them. First do this while processing each file in series. Second, do this in parallel on tombo.
3. Find the sum of squares in `./exercises/largefile.txt`. To do this, split it into `N` files, processing each one in parallel.
