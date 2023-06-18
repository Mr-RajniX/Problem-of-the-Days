## Problem of the Day - [<a href="https://leetcode.com/problems/restore-the-array/"> 1416. Restore The Array </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int MOD = 1000000007;
    int numberOfArrays(string s, int k) {
        int n = s.size();
        vector<int>dp(n + 1, 0);
        dp[n] = 1; 
        for (int startIdx = n - 1; startIdx >= 0; startIdx--)
        {
            long long currNum = 0, ways = 0;
            for (int i = startIdx; i < s.size(); i++){
                int currDig = s[i] - '0';
                currNum = (currNum * 10) + currDig; 
                if (currNum < 1 || currNum > k) break;
                int nextWays = dp[i + 1]; 
                ways = (ways +  nextWays) % MOD;
            }
            dp[startIdx] = ways;
        }
        return dp[0];
    }
</pre>
