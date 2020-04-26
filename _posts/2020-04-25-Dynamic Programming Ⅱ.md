---
layout:     post
title:      Dynamic Programming Ⅱ
date:       2020-04-25
author:     GSL
catalog: true
tags:
    - DP
---

Given an array A of non-negative integers, you are initially positioned at index 0 of the array. A[i] means the maximum jump distance from index i (you can only jump towards the end of the array). Determine the minimum number of jumps you need to reach the end of array. If you can not reach the end of the array, return -1.<br>

#### Assumptions<br>
The given array is not null and has length of at least 1.<br>

#### Examples<br>
{3, 3, 1, 0, 4}, the minimum jumps needed is 2 (jump to index 1 then to the end of array)><br>

{2, 1, 1, 0, 2}, you are not able to reach the end of array, return -1 in this case.<br>

#### Solution<br>
Assumptions: array is not null and is not empty
##### Base case:<br>
minJump[n-1] = 0 (n = array.length)
##### Induction rule:<br>
minJump[i] represents the min number of steps to jump from the index i to the last element

public class Solution {<br>
  public int minJump(int[] array) {<br>
    //Assumptions: array is not null and is not empty<br>
    int length = array.length;<br>
    int[] minJump = new int[length];<br>
    minJump[length-1] = 0;<br>
    for (int i = length-2; i >=0; i--) {<br>
    //initialize, -1 represents cannot jump from the index i to the last element<br>
      minJump[i] = -1;<br>
      if(array[i] + i >= length -1) {<br>
        minJump[i] =1;<br>
      } else{<br>
        int curMin = Integer.MAX_VALUE;<br>
        for(int j = array[i]; j>=1; j--) {<br>
          if (minJump[i+j] >0) {<br>
            curMin = Math.min(curMin, minJump[i+j]);<br>
          }<br>
        }<br>
        if (curMin < Integer.MAX_VALUE) {<br>
          minJump[i] = curMin +1;<br>
        }<br>
      }<br>
    }<br>
    return minJump[0];<br>
  }<br>
}<br>

Time: O(n^2)<br>
Space: O(n)
