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

## **Lowest common ancestor of Binary tree LC 235**

```cpp
class Solution {
public:
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
        if(root->val > p->val && root->val < q->val) return root;
        else if(root->val > p->val && root->val > q->val) return lowestCommonAncestor(root->left,p,q);
        else if(root->val < p->val && root->val < q->val) return lowestCommonAncestor(root->right,p,q);        
        else return root;
    }
};
```

## Validate BST LC 98

### Method-1 → Using max of trees (Brute force)

### Method-2 → In order traversal (cause in order traversal of BST is sorted)

```cpp
class Solution {
public:
    void Inorder(TreeNode* root,vector<int> &v){
        if(root==NULL) return;

        Inorder(root->left,v);
        v.push_back(root->val);
        Inorder(root->right,v);
    }
    bool isValidBST(TreeNode* root) {
        vector<int> v;
        Inorder(root,v);
        for(int i=0;i<v.size()-1;i++){
            if(v[i]<v[i+1]){
                continue;
            } 
            else return false;
        }
        return true;
    }
};
```

## Binary search Tree to Greater Sum Tree