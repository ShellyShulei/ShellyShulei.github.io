---
layout:     post
title:      Subset & Subsequence & Subarray
subtitle:   difference
date:       2020-04-04
author:     GSL
catalog: true
tags:
    - Subset
---




# 正文

## 
Let us take an array {1,2,3} and then we will try to define all the terms related to the given data set.

Subarray :- A subarray is a contiguous part of array (by contigous we mean we can't miss any element in between). So for above array we can write subarray as {1}, {2}, {3}, {1,2}, {2,3}, {1,2,3}.(Look we have taken contigous element). In general for a n-length array, we can have (n*(n+1))/2 total non-empty subarray.

Subsequence :- A subsequence need not be contiguous but needs to maintain the order. For the given array we can write subsequence as
{1}, {2}, {3}, {1,2}, {1,3}, {2,3}, {1,2,3} [Look how we have taken {1,3}, but ommited the same for subarray, because subarray is contigous] In general for a n-length array we can have (2^n -1) non-empty subsequence.


Subset :- A subset has no order and need not be contiguous. Again for the above data set {3,1}  [I.e {1,3} is same as {3,1}]is a valid subset but not a valid subsequence/subarray[ Not a valid subsequence because the order is disturbed and not a valid subarray because no order and not contigous]. In general, for an n-length array total no of the non-empty subset is (2^n-1) and the same as a subsequence.

#Conclusions
All subarrays are subsequences.
All subsequences are a subset.

