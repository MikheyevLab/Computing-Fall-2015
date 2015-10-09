---
layout: post
title: 4. Representations, Complexity and Algorithms
categories: []
tags:
  - news
published: true
---

# How does a Computer represent things
You might have heard that a computer works with something called *binary*. That means that everything you do with a computer boils down to a string of ones and zeros. As an example $00000100$ represent the number `4` in 8 bits. That also means that all operations (addition, subtraction, multiplication ...) is the manipulation of these binary strings. 8 *bits* are called one *byte* and there are $2^8 = 256$ different bit patterns for a byte. So with a byte we can represent 256 different *things*.

Sometimes instead of using binary string you will see people using hexadecimal numbers. Hexadecimal numbers from `00` to `FF` are exactly the binary patterns from `00000000` to `11111111`. ([Decimal, Hexadecimal, Octal, Binary](http://ascii.cl/conversion.htm)).

### Binary logic
One of the most fundamental things you can do with two bits, is binary logic or as it is also called boolean algebra.

#### `and` and `or`

| x | y | `x and y` | `x or y` |
|:-:|:-:|:---------:|:--------:|
| 0 | 0 |     0     |    0     |
| 0 | 1 |     0     |    1     |
| 1 | 0 |     0     |    1     |
| 1 | 1 |     1     |    1     |

#### `not`

|  x  | `not x` |
|:---:|:-------:|
|  0  |    1    |
|  1  |    0    |

#### `xor`
There is also the exclusive or (`xor`):

| x | y | `x xor y` |
|:---:|:---:|:---:|
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

But be careful if you use tools like `numpy`. They are implemented in `C` and you might get overflow behavior.

## Real numbers
For representing real numbers computer use floating point (defined in [IEEE754]). Floating point resembles scientific notation, but to the base of 2 instead of 10. One part of stores the significant and the other the exponent. For 64 bits [IEEE754] defines that 52 bits + 1 sign bit are reserved for the significant and 11 bits are reserved for the exponent.

Floating point numbers try to solve the problem of how to represent a set of infinite numbers with only a finite set of representations (bit patterns).

### Noteworthy features
 - Most numbers can't be exactly represented and errors accumulate.

    ```python
     print(100*0.1)
    sum = 0.0
    for i in range(0,100):
        sum += 0.1

    print(sum)
    ```

 - Gaps between numbers grow the bigger the numbers get.
 - Adding a small number to a big number might have no effect. This is called annihilation.
 - $(a+b)+c != a+(b+c)$ the order of addition matters!

    ```py
    a = 1e17
    b = -1e17
    c = 1

    (a + b) + c = ???
    a + (b + c) = ???
    ```
 - $a+b>a$ this is no longer true if the distance between $a$ and the next largest floating-point number is bigger than b $⇒ eps(a) > b$.
 - Instead of testing for equality you should test for approximaly equal.

### Further links
- [Python tutorial on Floating Point](https://docs.python.org/3.5/tutorial/floatingpoint.html)
- [What every computer scientist needs to know about floating point numbers](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.22.6768)
- [Floating point guids](http://floating-point-gui.de/formats/fp/)
- [Floating Point Numbers - Computerphile](https://www.youtube.com/watch?v=PZRI1IfStY0)
- [IEEE754](http://ieeexplore.ieee.org/xpl/mostRecentIssue.jsp?punumber=4610933)

# Complexity
The complexity of an algorithm is defined as the number of elementary steps an algorithm takes depending on the number of inputs.

The big *O* notation gives us the asymptotic runtime behavior of a function. As an example the search algorithm for a sorted list most of you implemented in the last homework runs in $O(n)$ steps. Constant cost factors are not of interest. The most optimal algorithm would run in $O(log(n))$. The sorting algorithm most of you implemented takes $O(n^2)$ and the most efficient algorithm takes $O(n*log(n))$.

If you notice that your program runs slowly for large datasets, there are several potential reasons. Either your implementation is inefficient or the algorithm you chose has a bad asymptotic runtime.

- [MIT 16.070](http://web.mit.edu/16.070/www/lecture/big_o.pdf)

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

# Linked-List
A linked list is a list that is build from elements that contain a *pointer* to the next element and the value they are storing.

```py
class LinkedList:
    next = None
    def __init__(self, value):
        self.value = value
    def append(self, value):
      if self.next == None:
          self.next = LinkedList(value)
      else:
          self.next.append(value)

```

# Operation costs in Python
The way we choose to represent data-structure leads to different cost of operations. As an example `append` takes $O(n)$ steps with your `LinkedList`. A more efficient implementation would take $O(1)$.

Take a look at operation costs for common python containers [TimeComplexity](https://wiki.python.org/moin/TimeComplexity) and a [detailed analysis of the python list.](http://www.laurentluce.com/posts/python-list-implementation/)

# Profiling in Python
Analyzing the performance of a program is called profiling. Profiling will determine hot spots in your code that are costly and those are the places that rewriting them might be beneficial.

- [The Python Profilers](https://docs.python.org/3.5/library/profile.html)
- [A guide to analyze Python performance](http://www.huyng.com/posts/python-performance-analysis/)
- [Profiling Python like a boss](https://zapier.com/engineering/profiling-python-boss/)
- [Timing and Profiling in IPython](http://pynash.org/2013/03/06/timing-and-profiling.html)

# Notes from last weeks homework

- `return` and *function arguments*
- markdown in Jupyter

# Homework

The homework is due on *October 15 2015* at *13:00pm* (eg. noon). Hand in your homework either as a IPython notebook or a pdf + the source code you wrote.

1. Implement a function that computes `xor`, while only using `and`, `or` and `not`.
2. What happens when you sort characters. What decides their order?
3. Write a program that takes 16 bit positive numbers (as list of boolean values) and converts them to decimal.
4. Implement bubble sort.
5. Implement merge sort.
6. Why is merge sort more efficient for large `n`?
7. Extend the defintion of `LinkedList` given in the lecture to support the operations:
    - `get(i)` get the value of the list element at position `i`.
    - `set(i, value)` set the value of the list element at position `i`.
    - `insert(i, value)` insert a new value at position `i`.
    - `delete(i)` delete the value at position `i`
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
9. What happens if you call `append` repeatedly on a python list. How could you prevent this behavior?
