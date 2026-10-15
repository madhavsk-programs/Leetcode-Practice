# Diameter of Binary Tree

## Problem Information
- **Platform:** Takeuforward
- **Difficulty:** Medium
- **URL:** https://takeuforward.org/practice/dsa/diameter-of-binary-tree
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

class Solution {
public:
    int height(TreeNode* root,int& dm){
        if(!root) return 0;
        int lh=height(root->left,dm);
        int rh=height(root->right,dm);
        dm=max(dm,lh+rh);
        return 1+max(lh,rh);
    }
    int diameterOfBinaryTree(TreeNode* root) {
        //your code goes here
        int dm=0;
        height(root,dm);
        return dm;
    }
};
```

---
*Generated automatically by LeetFeedback Extension*
