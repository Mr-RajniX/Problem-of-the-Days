## Problem of the Day - [<a href="https://leetcode.com/problems/make-array-strictly-increasing/"> 1187. Make Array Strictly Increasing </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  class Solution {
  private:
    const static int INF = 2001;
    const static int MX = 2000;
    
    int n;
    unordered_map<int, int> dp[MX];
    
    int find(int idx, int minval, vector<int> &a, vector<int> &b) {
        if(idx == n) return 0;
        if(dp[idx].find(minval) != dp[idx].end()) return dp[idx][minval];
        
        int val1 = a[idx] < minval ? INF : find(idx+1, a[idx]+1, a, b);
        auto it = lower_bound(b.begin(), b.end(), minval);
        int val2 = it == b.end() ? INF : 1+find(idx+1, *it+1, a, b);
        dp[idx][minval] = min(val1, val2);
        
        return dp[idx][minval];
    }
    
public:
    int makeArrayIncreasing(vector<int>& arr1, vector<int>& arr2) {
        n = arr1.size();
        sort(arr2.begin(), arr2.end());
        int ans = find(0, -1, arr1, arr2);
        return ans > n ? -1 : ans;
    }
};
</pre>
