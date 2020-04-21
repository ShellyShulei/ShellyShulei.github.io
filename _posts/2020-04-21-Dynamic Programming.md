---
layout:     post
title:      Dynamic Programming
date:       2020-04-21
author:     GSL
catalog: true
tags:
    - DP
---

## Dynamic Programming
### Fibonacci
First, let us look at the fibonacci. As we all know, it can be solved in recursive method.
![mark](http://q8ehknbjo.bkt.gdipper.com/blog/20200421/r6OcVDu8llP8.png?imageslim)
Time: O(2^n)<br>
However, recursive algorithms can be inefficient in terms of both time and space. We can use memoization to optimize it.<br>
![mark](http://q8ehknbjo.bkt.gdipper.com/blog/20200421/TKHpOyAIEIOc.png?imageslim)
Time:O(n)

### Longest Ascending SubArray
Given an unsorted array, find the length of the longest subarray in which the numbers are in ascending order.<br>
Assumptions:<br>
The given array is not null<br>

Examples:<br>
{7, 2, 3, 1, 5, 8, 9, 6}, longest ascending subarray is {1, 5, 8, 9}, length is 4.<br>

{1, 2, 3, 3, 4, 4, 5}, longest ascending subarray is {1, 2, 3}, length is 3.<br>

Base case: only one parameter M[0] = 1<br>
Induction rule: how to define the solution relationship from the small problem(s) to a larger problem<br>
a. M[i] represents within the range from the beginning to the ith element, the max length of the ascending subarray.(must include the ith element)<br>
b. M[i] = M[i-1] + 1                 if input[i-1] < input[i]<br>
               1                        otherwise<br>
![mark](http://q8ehknbjo.bkt.gdipper.com/blog/20200421/FVobVJNxfAsV.png?imageslim)

### Max Product Of Cutting Rope
Given a rope with positive integer-length n, how to cut the rope into m integer-length parts with length p[0], p[1], ...,p[m-1], in order to get the maximal product of p[0]*p[1]* ... *p[m-1]? m is determined by you and must be greater than 0 (at least one cut must be made). Return the max product you can have.

Assumptions<br>
n >= 2

Examples<br>
n = 12, the max product is 3 * 3 * 3 * 3 = 81(cut the rope into 4 pieces with length of each is 3).<br>

左大段 + 右小段  右边不可再分<br>
—— —— —— —— | ——<br>
例如：<br>
M[5] = Case 1: max(4, M[4]) *1<br>
       Case 2: max(3,M[3]) * 2<br>
       Case 3: max(2, M[2])*3<br>
       Case 4: max(1,M[1]) * 4<br>
![mark](http://q8ehknbjo.bkt.gdipper.com/blog/20200421/rHxk3jFscQPS.png?imageslim)

### Array Hopper I
Given an array A of non-negative integers, you are initially positioned at index 0 of the array. A[i] means the maximum jump distance from that position (you can only jump towards the end of the array). Determine if you are able to reach the last index.

Assumptions<br>
The given array is not null and has length of at least 1.<br>

Examples<br>
{1, 3, 2, 0, 3}, we are able to reach the end of array(jump to index 1 then reach the end of the array)<br>
{2, 1, 1, 0, 2}, we are not able to reach the end of array<br>

For excample:<br>
index   0  1  2  3  4<br>
input [ 2, 3, 1, 1, 4]<br>
M[]     T  T  T  T  T<br>
           <-----<br>
	   FROM RIGHT TO LEFT<br>
return M[0]<br>

Base case: M[4] = true, beacause A[4] is target itself<br>
Induction rule:<br>
M[i] represents whether I can jump form the ith element to the target element<br>
M[i] = true if  M[j]==true    or i + A[i] >= target<br>
              i<j<=i+A[i]   if i can jump to someplace j and j can reach the target<br>
       false   otherwise<br>
Time: O(n^2)<br>
![mark](http://q8ehknbjo.bkt.gdipper.com/blog/20200421/SxRA5UcriPtn.png?imageslim)







