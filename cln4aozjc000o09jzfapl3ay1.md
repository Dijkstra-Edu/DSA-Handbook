---
title: "Two Sum - Leetcode #1"
seoTitle: "Master the Two Sum Problem: Leetcode #1 Guide and Solutions"
seoDescription: "Explore the Ultimate Leetcode #1 Guide for Two Sum Problem. Find Expert Solutions, Step-by-Step Tutorials, and Pro Tips to Master this Coding Challenge. Ele"
datePublished: Fri Sep 29 2023 07:41:06 GMT+0000 (Coordinated Universal Time)
cuid: cln4aozjc000o09jzfapl3ay1
slug: two-sum-leetcode-1
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1695973144429/08fe4abc-412c-4c03-8fe3-ba9bc37f4f8a.png
tags: array, dsa, leetcode, dijkstra, easy-leetcode

---

---

### Question

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to* `target`.

You may assume that each input would have ***exactly* one solution**, and you may not use the *same* element twice.

You can return the answer in any order.

**Example 1:**

```plaintext
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**

```plaintext
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

**Example 3:**

```plaintext
Input: nums = [3,3], target = 6
Output: [0,1]
```

Link: [https://leetcode.com/problems/two-sum/](https://leetcode.com/problems/two-sum/)

---

### Intuition

* **Brute Force** - search for any two elements in two separate iterations to find any two numbers that add up to a given target.
    
    TC: O(n<sup>2</sup>)
    
    SC: O(1)
    
* **Optimized Solutions #1 - Two-pass Hashmap**
    
    * Place each value in the hashmap and its corresponding array element as a key in the first iteration, and on the second iteration, check if there exists any key such that key = target - arr\[i\]. If so, a solution has been found.
        
        TC: O(n)
        
        SC: O(n)
        
* **Optimized Solutions #2 - Two-pass Hashmap**
    
    * Same as #1, just with us checking if there exists a value within the hashmap that satisfies the condition before pushing the aforementioned key into the hashmap.
        
        TC: O(n)
        
        SC: O(n)
        

---

### Solution #1

```java
class Solution { // double pass
    public int[] twoSum(int[] nums, int target) {
        int arr[] = new int[2];
        HashMap<Integer, Integer> hmap = new HashMap<Integer, Integer>();

        for(int i=0; i<nums.length; i++) {
            hmap.put(nums[i],i);
        }
        for(int i=0; i<nums.length; i++) {
            if(hmap.containsKey(target-nums[i])) {
                arr[0] = hmap.get(target-nums[i]);
                arr[1] = i;
                break;
            }
        }
        return arr;
    }
}
```

### Solution #2

```java
class Solution { // single pass
    public int[] twoSum(int[] nums, int target) {
        int arr[] = new int[2];
        HashMap<Integer, Integer> hmap = new HashMap<Integer, Integer>();

        for(int i=0; i<nums.length; i++) {
            if(hmap.containsKey(target-nums[i])) {
                arr[0] = hmap.get(target-nums[i]);
                arr[1] = i;
                break;
            }
            hmap.put(nums[i],i);
        }
        return arr;
    }
}
```

---

### Links:

DSA Prep: [https://github.com/Dijkstra-Edu/DSA-Fundamentals---JAVA](https://github.com/Dijkstra-Edu/DSA-Fundamentals---JAVA)

Leetcode Solutions: [https://github.com/Dijkstra-Edu/LeetCode-Solutions](https://github.com/Dijkstra-Edu/LeetCode-Solutions)

Root Repository: [https://github.com/Dijkstra-Edu/DSA-Handbook](https://github.com/Dijkstra-Edu/DSA-Handbook)