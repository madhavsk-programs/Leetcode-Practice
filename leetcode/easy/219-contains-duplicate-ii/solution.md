# Contains Duplicate II

## Problem Information
- **Platform:** Leetcode
- **Difficulty:** Easy
- **URL:** https://leetcode.com/problems/contains-duplicate-ii/submissions/2143026238/
- **Date:** 2026-09-15

## Solution

```cpp
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {
        int n=nums.size();
        unordered_map<int,int>mpp;
        for(int i=0;i<n;i++){
            int num=nums[i];
            if(mpp.find(num)!=mpp.end()){
                int prevIndex=mpp[num];
                if(i-prevIndex<=k){
                    return true;
                }
            }
            mpp[num]=i;
        }
        return false;
    }
};
```

---
*Generated automatically by LeetFeedback Extension*
