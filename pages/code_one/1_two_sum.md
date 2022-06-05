---
title: 1-two-sum
tags: [getting_started]
keywords: two-sum, code, algorithm
last_updated: Feb 19, 2022
summary: "two-sum is a algorithm"
sidebar: mydoc_sidebar
permalink: 1_two_sum.html
folder: code_one
---

## Intro

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

## Solution

### S1 - Brute Force Algorithm

#### Python

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
```

#### JavaScript

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function (nums, target) {
  for (let i = 0; i < nums.length; i++) {
    for (let j = i + 1; j < nums.length; j++) {
      if (nums[i] + nums[j] == target) {
        return [i, j];
      }
    }
  }
};
```

#### Java

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i=0; i<nums.length; i++){
            for(int j=i+1; j<nums.length; j++){
                if(nums[i] + nums[j] == target){
                    return new int[] {i, j};
                }
            }
        }
        // return null if no result
        return null;
    }
}
```

### S2 - Brute Force Algorithm

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {}
        for i in range(len(nums)):
            hashmap[nums[i]] = i
        for i in range(len(nums)):
            cmpt = target - nums[i] # complement
            if cmpt in hashmap and hashmap[cmpt] != i:
                return [i, hashmap[cmpt]]
```

{% include links.html %}
