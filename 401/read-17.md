# CC16: Find Maximum Value in a Binary Tree

## Overview

The goal is to find the largest numeric value stored in a binary tree.

A **binary tree** is a data structure where each node can have up to two children: left and right.

## WHY — Why Is This Useful?

Finding the maximum value helps us understand how to traverse a tree, compare values, and process data stored in nodes.

## WHAT — What Is Required?

Create a method called `findMaximumValue()` for the Binary Tree class.

- **Arguments:** None
- **Returns:** Number
- **Goal:** Find the largest value in the tree.

## HOW — Algorithm Process

1. Start at the root node.
2. Set the initial maximum to the root's value.
3. Visit each node in the tree.
4. Compare the node's value to the current maximum.
5. Update the maximum if a larger value is found.
6. Return the maximum after checking all nodes.

## Example

```text
       10
      /  \
     5    20
    / \   /
   3   8 15
```

**Expected output:** `20`

## Approach and Efficiency

Using recursive depth-first traversal:

- **Time:** O(n) — Every node is visited once.
- **Space:** O(h) — Recursion uses space based on the tree's height.

## Key Concepts

- **Root:** The first node in a tree.
- **Node:** Stores a value and references to children.
- **Leaf:** A node without children.
- **Recursion:** A function calling itself to solve smaller parts of a problem.
- **Traversal:** Visiting nodes in a tree.

## Key Takeaway

Finding the maximum value requires examining every node because a regular binary tree does not guarantee that larger values are stored on a particular side.