## Problem of the Day - [<a href="https://leetcode.com/problems/longest-arithmetic-subsequence/"> 1027. Longest Arithmetic Subsequence </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int longestArithSeqLength(vector<int>& nums) {
        int n = nums.size();
        if (n <= 2)
            return n;

        int longest = 2;
        vector<unordered_map<int, int>> dp(n);

        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                int diff = nums[i] - nums[j];
                int cnt = 1;

                if(dp[j].count(diff))
                  cnt = dp[j][diff];

                dp[i][diff] = 1 + cnt;
                longest = max(longest, dp[i][diff]);
            }
        }

        return longest;
    }
</pre>
