---
tags: [machine-learning, programming]
---

2026-03-20 11:16

Status: #baby 

Tags: [[DSA]]

# Heap

## Complete Binary Tree
A **complete binary tree** is:

> A binary tree where **all levels are completely filled except possibly the last**, and the **last level is filled from left to right (no gaps).**

### Key points:

- Every level before the last → fully filled
    
- Last level → filled **left to right only**
    
- No “holes” in between nodes

        `1`
      `/   \`
      `2     3`
     `/ \    /`
     `4   5  6`
 
This is a complete tree

## Conditions for Heap
1. Should be a complete binary tree
2. Max Heap: Every parent node should be greater than its child node
3. Min Heap: Every parent node should be smaller than its children
#### ⚠️ Important Reality Check

- Heap is **NOT sorted**
    
- Only **parent-child relation matters**
    
- Siblings or subtrees can look random

## Application of Heap
Suppose we have three arrays -> 
1. (3, 17, 25, 78)
2. (9, 11, 13, 19)
3. (1, 88, 22, 65)
Now we can use heap to arrange this array into an ascending order
Step 1 - order the arrays in ascending order
Step 2 - 
# References

