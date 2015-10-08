---
layout: post
title: 4. Representations, Complexity and Algorithms
categories: []
tags:
  - news
published: false
---

# How does a Computer represent things
You might have heard that a computer works with something called *binary*. That means that everything you do with a computer boils down to a string of ones and zeros. As an example $00000100$ represent the number `4` in 8 bits. That also means that all operations (addition, subtraction, multiplication ...) is the manipulation of these binary strings. 8 *bits* are called one *byte* and there are $2^8 = 256$ different bit patterns for a byte. So with a byte we can represent 256 different *things*.

Sometimes instead of using binary string you will see people using hexadecimal numbers. Hexadecimal numbers from `00` to `FF` are exactly the binary patterns from `00000000` to `11111111`. ([Decimal, Hexadecimal, Octal, Binary](http://ascii.cl/conversion.htm)).

### Binary logic
One of the most fundamental things you can do with two bits, is binary logic or as it is also called boolean algebra.

#### `and` and `or`

| x | y | `x and y` | `x or y` |
|:-:|:-:|   :---:   |  :---:   |
| 0 | 0 |     0     |    0     |
| 0 | 1 |     0     |    1     |
| 1 | 0 |     0     |    1     |
| 1 | 1 |     1     |    1     |

#### `not`

|  x  | `not x` |
|:---:|  :---:  |
|  0  |    1    |
|  1  |    0    |

#### `xor`
There is also the exclusive or (`xor`):

| x | y | `x xor y` |
| --- | --- | --- |
|  0  |  0  |  0  |
|  0  |  1  |  1  |
|  1  |  0  |  1  |
|  1  |  1  |  0  |

## Text
Text in a computer is encoded either in [ASCII](http://ascii.cl/) or nowadays in one of the [Unicode standards](http://unicode.org/standard/standard.html) if you are wondering why your phone is able to send emoji and why we ASCII is not enough see these videos: [Internationalis(z)ing Code](https://www.youtube.com/watch?v=0j74jcxSunY) and [Emoji and the Levitating Businessman](https://www.youtube.com/watch?v=tITwM5GDIAI).

Python 3 uses [`UTF8`](https://docs.python.org/3/howto/unicode.html) as a default encoding. ASCII is a strict subset of the UTF-8 standard so as long as we only talk about the English 26 characters we will ignore unicode.

Words and sentences are then stored as arrays of characters. So if you work with strings you have to be as careful as when you work with arrays.

## Integers
We are back at the beginning of building computers and somebody asks you to create a computer that is able to do calculation with *positive* (or unsigned) numbers. Since no body told us how many numbers they need we decide to use 8 bit to store a numbers. We decide on the notion of storing the least significant number on the right (as in decimal) and we define $00000000$ to be zero. To convert a binary number into decimal we calculate $b_7 * 2^7 + b_6 * 2^6 + b_5 * 2^5 + b_4 * 2^4 + b_3 * 2^3 + b_2 * 2^2 + b_1 * 2^1 + b_0 * 2^0$, where $b_n$ corresponds to the $n$th bit from the right.

#### Addition

```
0001001
0000101
-------
0001110
```

##### Overflow

```
1101001
0110101
-------
0011110
```

How could we prevent this? Is this an intrinsic problem to how a computer handles math?

- [Binary Addition & Overflow - Computerphile](https://www.youtube.com/watch?v=WN8i5cwjkSE)

### Negative numbers
For negative numbers the first bit is reserved as the sign so with 8 bits we can represent numbers from -128 to 127. The particular representation that is used is called [2-complement](https://www.youtube.com/watch?v=lKTsv6iVxV4).

### Python and Integers
Python takes most of the worries away from you and when you add to very big numbers that could overflow it changes the representation from 32 to 64 bit. This allows you not to worry to much about stuff like this but it carries a performance penalty.

- Numpy

## Real numbers

- [Floating Point Numbers - Computerphile](https://www.youtube.com/watch?v=PZRI1IfStY0)

# Complexity

# Algorithms
## Sorting algorithms
- Bubble sort and merge sort [Getting Sorted - Computerphile](https://www.youtube.com/watch?v=kgBjXUE_Nwc)
- [Quick Sort - Computerphile](https://www.youtube.com/watch?v=XE4VP_8Y0BU)

## Searching in a sorted list

```
Search for 13 and 9
In: [0, 3, 5, 7, 8, 10, 13, 17]
                  8
                /    \
              5       13
            /   \    /   \
          3      7  10    17
          |
          0
```

The obvious solution is to go through each element in the list and check if it is the element we are looking for it. This is going to take $n = length(Inpu)$ number of operations in the average case. Another solution is to realize that a sorted list is a tree (with the root being `length(Input)/2`) and we can search a tree with `log(n)` operations.

# Data structures
## Linked Lists
## Array Lists
# Operation costs in Python
# Profiling in Python

# Notes from last weeks homework

- `return` and *function arguments*

# Homework

The homework is due on *October 15 2015* at *13:00pm* (eg. noon). Hand in your homework either as a IPython notebook or a pdf + the source code you wrote.

1. Implement a function that computes `xor`, while only using `and`, `or` and `not`.
2. What happens when you sort characters. What decides their order?
3. Write a program that takes 16 bit positive numbers (as list of boolean values) and converts them to decimal.
4. Implement bubble sort.
5. Implement merge sort.
6. Why is merge sort more efficient for large `n`?
7. Describe the following code using big-O notation, and justify your answer. Hint: if you are lost, profile this code.

    ```py
    # http://code.activestate.com/recipes/579093-converting-numeric-strings-to-integers/?in=lang-python
    def str_to_int(s):
        ctr = i = 0
        for c in reversed(s):
            i += (ord(c) - 48) * (10 ** ctr)
            ctr += 1
        return i

    print
    for s in ('0', '1', '2', '3', '12', '123', '234', '456', '567'):
        i = str_to_int(s)
        print "s = {}, i = {} |".format(s, i),

    print
    print

    for i in range(50):
        s = str(i)
        j = str_to_int(s)
        print "s = {}, j = {} |".format(s, j),
    ```

    To run this example you may need to install `pip install bipartite_recipe`

    ```py
    # http://code.activestate.com/recipes/579088-edge-coloring-of-a-bipartite-graph/?in=lang-python
    from bipartite_recipe import bipartite_match
    def max_degree(graph):
    	max_degree_u=max(len(v) for v in graph.values() )
    	count={}
    	for vlist in graph.values():
    		for v in vlist:
    			try:
    				count[v]+=1
    			except KeyError:
    				count[v]=1
    	max_degree_v=max(count.values())
    	return max(max_degree_v,max_degree_u)
    def best_match(graph):
    	b_m=bipartiteMatch(graph)[0]
    	return dict((value,key) for (key,value) in b_m.items())
    def edge_coloring(graph):
    	g=graph.copy()
    	number_colors=max_degree(g)
    	for color in range(number_colors):
    		print 'NEXT COLOR'
    		bm=best_match(g)
    		print bm
    		for k in g.copy():
    			try:
    				g[k].remove(bm[k])
    			except KeyError:
    				pass

    graph={ 'p1':['c1','c3'], 'p2':['c1','c2'], 'p3':['c2','c3'], 'p4':['c2'] }
    edge_coloring(graph)
    ```

    ```py
    # http://code.activestate.com/recipes/578959-draw-a-diamond-with-asterisks-using-recursion/?in=lang-python
    def triangles(n):
        if not n & 1:
            raise ValueError('n must be odd')
        print_diamond(0, n, n >> 1)

    def print_diamond(start, stop, midpoint):
        if start < stop:
            if start <= midpoint:
                print('  ' * (midpoint - start) + '* ' * ((start << 1) + 1))
            else:
                print('  ' * (start - midpoint) + '* ' * ((stop - start << 1) - 1))
            print_diamond(start + 1, stop, midpoint)
    ```        

8. Consider the following code in Python:

    ```py
    a = {'foo': 'bar'}
    b = a

    b['new'] = 'key'
    print(a)
    ```
Is this behavior what you expected? Why does Python do this? What would you do if you wanted to change just _b_ and not _a_?