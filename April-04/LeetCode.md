## Problem of the Day - [<a href="https://leetcode.com/problems/optimal-partition-of-string/description/"> 2405. Optimal Partition of String </a>]


#### ⭐<ins>Solution Function Code</ins> -

    int partitionString(string s) {
        int xr=0,ans=1;
        for(int i=0;i<s.size();i++){
            if(xr&(1<<(s[i]-'a'))){
                xr=0;
                ans++;
            }
            xr^=(1<<(s[i]-'a'));
        }
        return ans;
    }

