# Max Consecutive Ones III

## Problem Information
- **Platform:** Leetcode
- **Difficulty:** Medium
- **URL:** https://leetcode.com/problems/max-consecutive-ones-iii/submissions/2143060062/
- **Date:** 2026-09-15

## Solution

```cpp
class Solution {
public:
    int longestOnes(vector<int>& nums, int k) {
        int n = nums.size();
        int l = 0;
        int zr = 0,maxlen=0;
        for (int r = 0; r < n; r++) {
            if (nums[r] == 0) {
                zr++;
            }
            while (zr>k) {
                if (nums[l]==0) {
                    zr--;
                }
                l++;
            }
            maxlen=max(maxlen,r-l+1);
        }
        return maxlen;
    }
};
```

---
*Generated automatically by LeetFeedback Extension*
