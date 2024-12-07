# Tree Data Structures and Algorithms

## Table of Contents
1. [Introduction to Trees](#introduction-to-trees)
    - [Generic Trees](#generic-trees)
    - [Binary Trees](#binary-trees)
    - [Binary Search Trees](#binary-search-trees)
    - [AVL Trees](#avl-trees)
2. [Tree Operations](#tree-operations)
    - [Display Tree](#display-tree)
    - [Find Sum of Tree Nodes](#find-sum-of-tree-nodes)
    - [Find Size of Tree](#find-size-of-tree)
    - [Find Node with Max Value](#find-node-with-max-value)
    - [Find the Level of the Tree](#find-the-level-of-the-tree)
3. [Types of Binary Trees](#types-of-binary-trees)
4. [Common Problems](#common-problems)
    - [Diameter of Binary Tree (LC 543)](#diameter-of-binary-tree-lc-543)
    - [Same Tree (LC 100)](#same-tree-lc-100)
    - [Invert Binary Tree](#invert-binary-tree)
    - [Binary Tree Paths](#binary-tree-paths)
    - [Lowest Common Ancestor (LC 236)](#lowest-common-ancestor-lc-236)

---

## Introduction to Trees

### Generic Trees
A generic tree is a data structure in which each node can have zero or more child nodes.

### Binary Trees
A binary tree is a tree structure where each node has at most two children, referred to as the left child and the right child.

### Binary Search Trees
A binary search tree (BST) is a binary tree with the following properties:
- The left subtree of a node contains only nodes with values less than the node's value.
- The right subtree of a node contains only nodes with values greater than the node's value.

### AVL Trees
An AVL tree is a self-balancing binary search tree. It maintains the height balance property:
- The difference between the heights of the left and right subtrees cannot be more than one for any node.

---

## Tree Operations

### Display Tree
```cpp
void displayTree(Node* root){
    if (root == NULL) return;

    cout << root->val << "  ";
    displayTree(root->left);
    displayTree(root->right);
}

