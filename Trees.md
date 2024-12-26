# **Binary Trees -1**

## **Introduction to trees**

- **GENERIC TREES**
- **BINARY TREES**
- **BINARY SEARCH TREES (right part greater than left)**
- **AVL Trees (balanced BST)**

## **Display tree**

## **Code implementation**

```cpp
**void displayTree(Node* root){
    if(root==NULL) return ;

    cout<<root->val<<"  ";

    displayTree(root->left);
    displayTree(root->right);

}**
```

## **Find sum of tree nodes**

```cpp
**int sum(Node* root){
        if(root==NULL) return 0; 

       return root->val + sum(root->left) + sum(root->right);

}**
```

## **Find size of tree**

```cpp
**int siz(Node* root){
    if(root==NULL) return 0;

    return 1+siz(root->left) + siz(root->right);
}**

```

## **Find node with max value**

```cpp
**#include<climits>

int more(Node* root){
    if(root==NULL) return INT_MIN;

    return max(root->val,max(more(root->left),more(root->right)));

}**
```

## **Find the level of the tree**

```cpp
**int level(Node* root){
    if(root==NULL) return 0;

    return 1+max(level(root->left),level(root->right));
}** 
```

## **Types of binary trees**

- **Full Binary tree**
- **perfect Binary tree**
- **complete binary tree (last level will not be completed)Left to right**
- **Balancedd Binary tree   (avl condition)**
- **Degenerated and skewed Binary trees (has 0 or 1 child)**

## **Diameter of binary trees LC 543**

```cpp
**class Solution {
public:

    int level(TreeNode* root){
        if(root==NULL) return 0;

        return 1+ max(level(root->left),level(root->right));
    }
    int diameterOfBinaryTree(TreeNode* root) {
        if(root==NULL) return 0;
        return max(level(root->left)+ level(root->right), max(diameterOfBinaryTree(root->left),diameterOfBinaryTree(root->right)));
    }
};**
```

## **Same tree LC 100**

```cpp
**class Solution {
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
};**
```

## **Invert Binary Tree**

```cpp
**class Solution {
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
};**
```

## **Binary tree path inform of string**

```cpp
**class Solution {
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
};**
```

## **Lowest common ancestor of Binary tree LC 236 (IMP)**

```cpp
**class Solution {
public:

    bool exists(TreeNode* root, TreeNode* target){
        if(root==NULL) return false;
        if(root==target) return true;
        return exists(root->left,target) || exists(root->right,target);

    }

    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
        if(root==p || root==q) return root;
        else if (exists(root->left,p) && exists(root->right,q)) return root;
        else if (exists(root->right,p) && exists(root->left,q)) return root; 
        else if (exists(root->left,p) && exists(root->left,q)) return lowestCommonAncestor(root->left,p,q);
        else return lowestCommonAncestor(root->right,p,q);      

    }
};**
```

# **Binary trees -2**

## **Traversal in Trees→ To visit every node**

### **DFS,BFS,Moris Traversal**

### **Preorder (Root left Right)**

```cpp
**void displayTree(Node* root){
    if(root==NULL) return ;

    cout<<root->val<<"  ";

    displayTree(root->left);
    displayTree(root->right);

}**
```

### **In order (Left Root Right)**

```cpp
**void displayTree(Node* root){
    if(root==NULL) return ;

    displayTree(root->left);
    cout<<root->val<<"  ";
    displayTree(root->right);
}**
```

### **Post order (Left Right Root)**

```cpp
**void displayTree(Node* root){
    if(root==NULL) return ;

    displayTree(root->left);
    displayTree(root->right);
    cout<<root->val<<"  ";
}**
```

## **Print elements of nth level**

```cpp
**void displaynth(Node* root,int curr,int level){
    if(root==NULL) return;
    if(curr==level){
     cout<<root->val<<" ";
     return}
    displaynth(root->left,curr+1,level);
    displaynth(root->right,curr+1,level);
 }**
```

## **IN preorder**

**T.C = O(N)**

**S.C = O(levels+1) , O(h+2) or O(h)**

## **Level order traversal (Right to left) LC 102**

```cpp
**class Solution {
public:
    void nth(TreeNode* root,int curr,int lev,vector<int> &v){
        if(root==NULL) return;
        if(curr==lev){
            v.push_back(root->val);
            return;
        }
        nth(root->left,curr+1,lev,v);
        nth(root->right,curr+1,lev,v);
    }
    void lOrder(TreeNode* root,vector<vector<int>> &ans){
        int n=level(root);
        for(int i=1;i<=n;i++){
            vector<int> v;
            nth(root,1,i,v);
            ans.push_back(v);

        }

    }
    int level(TreeNode* root){
        if(root==NULL) return 0;
        return 1+ max(level(root->left),level(root->right));
    }
    vector<vector<int>> levelOrder(TreeNode* root) {
        vector<vector<int>> ans;
        lOrder(root,ans);
        return ans;
    }
};**
```

## **Level order in Zigzag manner LC 103**