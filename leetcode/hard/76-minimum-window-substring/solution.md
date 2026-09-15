# Minimum Window Substring

## Problem Information
- **Platform:** Leetcode
- **Difficulty:** Hard
- **URL:** https://leetcode.com/problems/minimum-window-substring/submissions/2142952489/
- **Date:** 2026-09-15

## Solution

```cpp
class Solution {
public:
    string minWindow(string s, string t) {
        int minlen=INT_MAX;
        int sindex=-1;
        int hash[256]={0};
        for(int c:t){
            hash[c]++;
        }
        int cnt=0;
        int l=0,r=0;
        while(r<s.size()){
            if(hash[s[r]]>0){
                cnt++;
            }
            hash[s[r]]--;
            while(cnt==t.size()){
                if(r-l+1<minlen){
                    minlen=r-l+1;
                    sindex=l;
                }
                hash[s[l]]++;
                if(hash[s[l]]>0){
                    cnt--;
                }
                l++;
            }
            r++;
        }
        return (sindex==-1)?"":s.substr(sindex,minlen);
    }
};
```

---
*Generated automatically by LeetFeedback Extension*
