# Two Sum

## Problem Information
- **Platform:** Leetcode
- **Difficulty:** Easy
- **URL:** https://leetcode.com/problems/two-sum/submissions/2143053388/
- **Date:** 2026-09-15

## Solution

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n=nums.size();
        unordered_map<int,int> mpp;
        for(int i=0;i<n;i++){
            int num=nums[i];
            int need=target-num;
            if(mpp.find(need)!=mpp.end()){
                return {mpp[need],i};
            }
            mpp[num]=i;
        }
        return {-1,-1};
    }
};
```

---
*Generated automatically by LeetFeedback Extension*
