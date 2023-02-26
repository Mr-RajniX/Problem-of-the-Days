## Problem of the Day - [<a href="https://leetcode.com/problems/edit-distance/description/"> 72. Edit Distance</a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int minDistance(string word1, string word2) {
        int m = word1.length();
        int n = word2.length();
        int dp[m+1][n+1];
        for (int i = 0; i <= m; i++) {
            dp[i][0] = i;
        }
        for (int j = 0; j <= n; j++) {
            dp[0][j] = j;
        }
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (word1[i-1] == word2[j-1]) {
                    dp[i][j] = dp[i-1][j-1];
                } 
                else {
                    int insertOp = dp[i][j-1]; 
                    int deleteOp = dp[i-1][j]; 
                    int replaceOp = dp[i-1][j-1]; 
                    dp[i][j] = 1 + min({insertOp, deleteOp, replaceOp});
                }
            }
        }
        return dp[m][n];
    }
</pre>
