# Binary search tree

- Efficient searching , insertion and deletion
- Implementing data structures like sets,maps and priority queues

## Search in BST LC 700

```cpp
class Solution {
public:
    TreeNode* searchBST(TreeNode* root, int val) {
        if(root==NULL) return NULL;
        else if(root->val==val ) return root;
        else if(root->val > val) return searchBST(root->left,val);
        else return searchBST(root->right,val);

    }
};
```

## Insert into BST LC 701

```cpp
class Solution {
public:
    TreeNode* insertIntoBST(TreeNode* root, int val) {
        if(root==NULL) return new TreeNode(val);
        // if(root->val > val && root->left==NULL ) return root;
        // if(root->val < val && root->right==NULL ) return root;

        if(root->val > val) {
        if(root->left==NULL) {
        root->left=new TreeNode(val);
        return root;
        }
        else  insertIntoBST(root->left,val);
        }
        else if(root->right==NULL) {
        root->right=new TreeNode(val);
        return root;
        }
        else  insertIntoBST(root->right,val);
        return root;

    }   
};
```
