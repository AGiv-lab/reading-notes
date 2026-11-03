# Reading 15: Trees

## Overview

Trees are data structures that organize information in a hierarchy using nodes and connections.

### Key Terminology

- **Node:** Stores a value and references to other nodes.
- **Root:** The first node in a tree.
- **Edge:** Connection between two nodes.
- **Leaf:** A node without children.
- **Height:** Number of edges from the root to the furthest leaf.
- **Binary Tree:** Each node has at most two children.
- **K-ary Tree:** Each node can have up to K children.
- **Binary Search Tree (BST):** Smaller values go left; larger values go right.

## WHY — Why Use Trees?

Trees help organize hierarchical information and support searching, sorting, and traversing data.

Examples include file systems, organizational charts, and search structures.

## WHAT — Tree Traversal

Traversal means visiting the nodes of a tree in a specific order.

### Example Binary Tree

```text
       A
      / \
     B   C
    / \  /
   D   E F
```

### Depth-First Traversal (DFS)

DFS explores branches before moving to other branches.

| Method | Order | Result |
|---|---|---|
| Pre-order | Root → Left → Right | A, B, D, E, C, F |
| In-order | Left → Root → Right | D, B, E, A, F, C |
| Post-order | Left → Right → Root | D, E, B, F, C, A |

**Recursion** is commonly used for DFS.

### Breadth-First Traversal (BFS)

BFS visits nodes level by level, using a **FIFO queue**.

**Result:** A, B, C, D, E, F

## HOW — Breadth-First Traversal

1. Add the root to a queue.
2. Remove the first node and record its value.
3. Add its left and right children to the queue.
4. Repeat until the queue is empty.

**Example:**

```text
Queue: [A]
Visit A → Queue: [B, C]
Visit B → Queue: [C, D, E]
Visit C → Queue: [D, E, F]
```

## Binary Tree vs. Binary Search Tree

**Binary Tree:** No required sorting order.

**Binary Search Tree:** Values are organized so smaller values are left and larger values are right.

### BST Search Example

```text
       20
      /  \
    10    30
   /  \
  5   15
```

To find `15`:

1. Start at `20`.
2. `15 < 20` → Go left.
3. `15 > 10` → Go right.
4. Find `15`.

## Big O Efficiency

| Operation | Time Complexity |
|---|---|
| Binary Tree search | O(n) |
| Binary Tree insertion using BFS | O(n) |
| Balanced BST search | O(log n) |
| Unbalanced BST search | O(n) |
| DFS traversal | O(n) |
| BFS traversal | O(n) |

**Key idea:** A balanced BST can search faster because it eliminates parts of the tree from consideration.

## Key Takeaway

Trees organize data hierarchically. DFS explores branches, while BFS explores levels. Binary Search Trees use ordering rules to make searching more efficient when the tree is balanced.

## Resource

[Trees — Code 401 Curriculum](https://gicw.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/trees.html)