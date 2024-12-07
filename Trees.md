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

## Find sum of tree nodes

```cpp
int sum(Node* root){
        if(root==NULL) return 0; 

       return root->val + sum(root->left) + sum(root->right);

}
```

## Find size of tree

```cpp
int siz(Node* root){
    if(root==NULL) return 0;

    return 1+siz(root->left) + siz(root->right);
}

```

## Find node with max value

```cpp
#include<climits>

int more(Node* root){
    if(root==NULL) return INT_MIN;

    return max(root->val,max(more(root->left),more(root->right)));

}
```

## Find the level of the tree

```cpp
int level(Node* root){
    if(root==NULL) return 0;

    return 1+max(level(root->left),level(root->right));
}
```

## Types of binary trees

- Full Binary tree
- perfect Binary tree
- complete binary tree (last level will not be completed)Left to right
- Balancedd Binary tree   (avl condition)
- Degenerated and skewed Binary trees (has 0 or 1 child)

## Diameter of binary trees LC 543

```cpp
class Solution {
public:

    int level(TreeNode* root){
        if(root==NULL) return 0;

        return 1+ max(level(root->left),level(root->right));
    }
    int diameterOfBinaryTree(TreeNode* root) {
        if(root==NULL) return 0;
        return max(level(root->left)+ level(root->right), max(diameterOfBinaryTree(root->left),diameterOfBinaryTree(root->right)));
    }
};
```

## Same tree LC 100

```cpp
class Solution {
public:
    bool isSameTree(TreeNode* p, TreeNode* q) {
        if(p==NULL && q==NULL) return true;
        if(p==NULL && q!=NULL) return false;
        if(p!=NULL && q==NULL) return false;
        
        if(p->val != q->val) return false;
        if(isSameTree(p->left,q->left)==false) return false;
        if(isSameTree(p->right,q->right)==false) return false;

        return true;
    }
};
```

## Invert Binary Tree

```cpp
class Solution {
public:

void helper(TreeNode* root){
    if(root==NULL) return ;

    TreeNode* temp=root->left;
    root->left=root->right;
    root->right=temp;
    helper(root->left);
    helper(root->right);

}
    TreeNode* invertTree(TreeNode* root) {
        helper(root);
        return root;
    }
};
```

## Binary tree path inform of string

```cpp
class Solution {
public:

void helper(TreeNode* root,string s,vector<string>& ans){
    if(root==NULL) return;
    string a=to_string(root->val);
    if(root->left==NULL && root->right==NULL) {
        s+=a;
        ans.push_back(s);
        return ;
    }
     helper(root->left,s+a+"->", ans);
     helper(root->right,s+a+"->", ans);

}
    vector<string> binaryTreePaths(TreeNode* root) {
        vector<string> ans;
        helper(root,"",ans);

        return ans;

    }
};
```

## Lowest common ancestor of Binary tree LC 236 (IMP)

