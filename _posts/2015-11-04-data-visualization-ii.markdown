---
layout: post
title: "Data visualization II"
date: "2015-11-06"
---

# Making interactive plots

For most of human history we have been limited to using static 2D materials to visualize information (clay tablets, paper, etc.). You can add a third dimension using projections (almost always a bad idea), or colors and shapes, as we did in the last lecture. 2D visualizations worked really well in most cases, and for most of human history.

But graphs need not be static. With the advent of computers we have increasingly powerful ways to interact with data, or to present them in a way that users can explore different views, or draw their own conclusions. Interactive visualization was first pioneered not by scientists but by the media, as a way of making graphs more appealing. In fact, a leader in this field has actually been the [New York Times](https://github.com/mbostock/d3/wiki/Gallery#the-new-york-times-visualizations), who for a while employed a rock star data visualization expert to work on an interactive library called [D3](http://d3js.org), which stands for Data Driven Documents. In this lecture we will work through a D3 tutorial to make an interactive plot. All you need is your browser. And you get to learn a bit of yet another language -- JavaScript, the most popular computer language in the world!

<script type="text/javascript" src="//www.google.com/trends/embed.js?hl=en-US&q=javascript,+python,+/m/0212jm&date=1/2010+61m&cmpt=q&tz=Etc/GMT-9&tz=Etc/GMT-9&content=1&cid=TIMESERIES_GRAPH_0&export=5&w=500&h=330"></script>

Note: The "Python" term includes actual pythons, although I suspect its recent popularity has been mostly due to the programming language.

The process of making D3 plots is actually a bit involved, requiring, besides javascript, knowledge of how web pages are made and served to the user. This is done most excellently in the free online ebook [Interactive Data Visualization for the Web](http://chimera.labs.oreilly.com/books/1230000000345/). I can't do any better than that. So, go ahead and read chapters 1-7, and do the exercises.

## Where to host your beautiful plot?
One of the things you will realize, is that at this point the plots exist only on your computer. What if you want to share them with the world?

If you have your own hosted web page, you can put them there, of course. You can also put them in the Public folder of Dropbox and share the link to the html file. A better way to host the images is together with your source code using [github pages](https://pages.github.com). You can have github generate and host a web site by going to "Settings: Launch Automatic page generator" on any repository. This allows you to have a web site for every project. This is actually good way to organize and present supplementary data for manuscripts, including interactive figures, which most (almost all?) journals can't handle at this time.

## Inspiration
- [D3 Gallery](https://github.com/mbostock/d3/wiki/Gallery)
- [More D3](http://bl.ocks.org/mbostock)
- [Introduction to ML](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/)
- Hans Rosling:
  - [Ted Talk 2006](http://www.ted.com/talks/hans_rosling_shows_the_best_stats_you_ve_ever_seen)
  - [BBC] (https://www.youtube.com/watch?v=jbkSRLYSojo)
- [Points of View - Nature Methods](http://clearscience.info/wp/?p=546)


## Homework
Submit the homework in as a github repository, hosted on gh-pages.
1. Read [Interactive Data Visualization for the Web](http://chimera.labs.oreilly.com/books/1230000000345/) chapters 1-7, and implement the basic scatter plot
- Implement the [force-directed layout](http://chimera.labs.oreilly.com/books/1230000000345/ch11.html#_force_layout).
- Now modify the layout so that the names of each node appear when you hover over the points.
- Using any data set of your choice
