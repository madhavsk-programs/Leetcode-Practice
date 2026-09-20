# Find Pivot Index

## Problem Information
- **Platform:** Leetcode
- **Difficulty:** Easy
- **URL:** https://leetcode.com/problems/find-pivot-index/submissions/2147886863/
- **Date:** 2026-09-20

## Solution

```cpp
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
       int n=nums.size();
       int total=0;
       for(int x:nums){
         total+=x;
       } 
       int left=0;
       for(int i=0;i<n;i++){
        int right=total-left-nums[i];
        if(right==left){
            return i;
        }
        left+=nums[i];
       }
       return -1;

    }
};
```

---
*Generated automatically by LeetFeedback Extension*
