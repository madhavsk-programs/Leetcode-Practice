# Check for balanced binary tree

## Problem Information
- **Platform:** Takeuforward
- **Difficulty:** Medium
- **URL:** https://takeuforward.org/practice/dsa/check-for-balanced-binary-tree
- **Date:** 2026-10-15

## Solution

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int data;
 *     TreeNode *left;
 *     TreeNode *right;
 *      TreeNode(int val) : data(val) , left(nullptr) , right(nullptr) {}
 * };
 **/

class Solution{
public:
    int height(TreeNode* root){
        if(root==nullptr) return 0;
        int lh=height(root->left);
        int rh=height(root->right);
        return max(lh,rh)+1;
    }
    bool isBalanced(TreeNode *root){
    	//your code goes here
        if(root==nullptr) return true;
        int lh=height(root->left);
        int rh=height(root->right);
        if(abs(lh-rh)>1) return false;

        return isBalanced(root->left) && isBalanced(root->right);
    }
};
```

---
*Generated automatically by LeetFeedback Extension*
