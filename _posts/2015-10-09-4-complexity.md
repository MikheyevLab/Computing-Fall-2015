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
7. What is the complexity in O() for the following codes:
8. Floating-point numerical stability
9. Profile and improve upon the following codes:
