## Problem of the Day - [<a href="https://leetcode.com/problems/number-of-ways-to-form-a-target-string-given-a-dictionary/description/"> 1639. Number of Ways to Form a Target String Given a Dictionary </a>]


#### ⭐<ins>Solution Function Code </ins> -
<pre>

    int numWays(vector<string>& words, string target) {
        int mod = 1e9 + 7;
        int m = words.size(), n = words[0].size();
        vector<vector<int>> freq(n, vector<int>(26, 0));
        for (int j = 0; j < n; j++) {
            for (int i = 0; i < m; i++) {
                freq[j][words[i][j] - 'a']++;
            }
        }
        vector<long long> dp(target.size() + 1, 0);
        dp[0] = 1;
        for (int j = 0; j < n; j++) {
            for (int i = target.size(); i > 0; i--) {
                dp[i] = (dp[i] + dp[i-1] * freq[j][target[i-1] - 'a']) % mod;
            }
        }
        
        return dp[target.size()];
    }
</pre>
