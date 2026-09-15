# Minimum Size Subarray Sum

## Problem Information
- **Platform:** Leetcode
- **Difficulty:** Medium
- **URL:** https://leetcode.com/problems/minimum-size-subarray-sum/submissions/2142964362/
- **Date:** 2026-09-15

## Solution

```cpp
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int l=0;
        int sum=0;
        int minlen=INT_MAX;
        for(int r=0;r<nums.size();r++){
            sum+=nums[r];
            while(sum>=target){
                minlen=min(minlen,r-l+1);
                sum-=nums[l];
                l++;
            }
        }
        if(minlen==INT_MAX) return 0;
        return minlen;

    }
};
```

---
*Generated automatically by LeetFeedback Extension*
