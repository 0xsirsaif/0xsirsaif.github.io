---
layout: post
title: Implementing an LSM Tree - Learning Log (Part 1)
categories: databases
author: saif
---

## Timeline

- **2025-11-16**:

  - I understand the basics and the theory about LSM Trees implementation. It all starts with understanding and implementing one of the most important components of LSM Trees: the memtable, memtable is implemented using an in-memory sorted data structure: AVL Tree, Skip List, Red-Black Tree, etc.
  - I am focusing in implementing the memtable using a Skip List.
  - resources:

    - Data Structures and Algorithms in Python, book. I have read this book before so, i am starting with reviewing relevant chapters.

  - Skip List implementation thought process:

    - Skip list search and update operations time complexity: O(log n)
    - Skip list is a multi-layer data structure, each layer consists of a subset of its items.
    - There's a sential objects guarding the borders of each layer −∞ and +∞. we have multiple choices for sential object representations depending on what kind of operations and keys we're going to store in the map: floats only, arbitrary hashable objects like strings and tuples, etc.
    - Each node will be an object with `right`, `left`, `up`, `down` methods. (There's a clever and optimized version for implementing towers, but we stick with this educational implementation)
    - search algorithm: 0) start at the topmost, left position (_start position_) 1) unless we're not in the bottom layer (`node.down == None`), drop down to the lower level in the present tower (`node = node.down`) 2) move to the right until it's the rightmost position on the present level such that its _key_ is less than or equal to the key we search for (_scan forward process_) 3) return to step 1
- **2025-11-23**
  - Skip List Implementation
