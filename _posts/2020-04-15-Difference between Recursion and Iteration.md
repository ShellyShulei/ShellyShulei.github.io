---
layout:     post
title:      Difference between Recursion and Iteration
date:       2020-04-15
author:     GSL
catalog: true
tags:
    - Java
    - Recursion
    - Iterative
---



### A program is called recursive when an entity calls itself. A program is call iterative when there is a loop (or repetition).

### Recursion
Boil down a big problem to smaller ones(size n depends on size n-1,or n-2, or... n/2)
#### Implementation
1) Base Case: smallest problem to solve <br>
2) Recursion rule: how to make the problem smaller(if we can resolve same problem but with a smaller size, the what is left to do for the current problem size n)

#### Factorial Example
Recursion is great for processing data and performing mathematical calculations. Computing a number's factorial serves as a great example of how to use recursion in Java.

Here is an example of using recursion to determine a number's factorial:
![mark](http://q8ehknbjo.bkt.gdipper.com/blog/20200415/6lY3zHoF0ytE.png?imageslim)

In this example, our factorialRecursive function calls itself repeatedly until theNumber equals 1. 

#### Time and Space complexity of recursive function
![mark](http://q8ehknbjo.bkt.gdipper.com/blog/20200415/v8E84QCQuuQJ.png?imageslim)


### Iteration
In Java, iteration is a technique used to sequence through a block of code repeatedly until a specific condition either exists or no longer exists. Iterations are a very common approach used with loops.

#### Factorial Example
We can use also iteration to calculate a number's factorial. The implementation below uses a for loop that iterates sequentially from 1 through the starting value of the provided number (theNumber).

Here is the code:
![mark](http://q8ehknbjo.bkt.gdipper.com/blog/20200415/UBEBYFlb5Phw.png?imageslim)


	

