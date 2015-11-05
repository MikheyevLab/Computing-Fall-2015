---
layout: post
title: "Data visualization I"
date: "2015-10-30"
---

Data visualization is one of the most important and difficult skills to master for scientific communication. Each graphic has to tell a story.

# Philosophy

    "Above all else show the data"

    "A large share of ink on a graphic should present
     data-information, the ink changing as the data change.
      Data-ink is the non-erasable core of a graphic, the
       non-redundant ink arranged in response to variation
        in the numbers represented"

    Tufte, 1983, The Visual Display of Quantitative Information

A good plot should tell a complete story. For instance, this one tells the story of Napoleon's Grande Armée:

![](http://comicscomicsmag.com/wp-content/uploads/big_march2.jpg)

Even something boring can be made to look interesting:

![](http://www.daveliepmann.com/tufte-css/img/exports-imports.png)

## Intro to ggplot2

Notebook [here](../ggplot2 intro.html).

## Links
- [R Cookbook](http://www.cookbook-r.com/Graphs/) Indespensible reference for how to do things with ggplot2
- [ggplot2 cheatsheet](http://zevross.com/blog/2014/08/04/beautiful-plotting-in-r-a-ggplot2-cheatsheet-3/) Good concise reference
- [Intro to ggplot2](http://chrisladroue.com/extra/ggplot2Intro/introductionGGplot2/) Well done lecture using

## In-class exercise

- Using the Iris data set, make a plot that clearly separates the three species along two morphological axes.

## Homework
1. Using any appropriate data set, create the following types of plots
  - a violin plot
  - a rug plot
  - a scatterplot with groups of points, but without a legend
  - A scatterplot without x-axis ticks
  - annotate a plot with text
- Take two separate plots in made usig ggplot and arrange them in in columns (_not_ using facet_grid). Hint: you will need to use another library.
- Draw a histogram of points with a fitted normal distribution (this looks better if your data are roughly normally distributed). E.g., [here](http://www.nature.com/ncomms/2015/150806/ncomms8991/images/ncomms8991-f2.jpg)
- Implement some plots using the ggplot libary in Python
- Using Titanic survivor data, make a plot to show whether "women and children first" changed the odds of survival. Was economic class a factor?
- Make a chord diagram in R, using any library and data set
