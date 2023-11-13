#### Problem of the Day : [Shortest Common Supersequence](https://www.geeksforgeeks.org/problems/shortest-common-supersequence0322/1)

#### Solution :
<pre>
  int shortestCommonSupersequence(string X, string Y, int m, int n){
        vector< vector< int>>dp(m + 1, vector< int>(n + 1, 0));
        for(int i = m - 1; i >= 0; i--){
            for(int j = n - 1; j >=0; j--){
                if(X[i] == Y[j])
                dp[i][j] = 1 + dp[i + 1][j + 1];
                else 
                dp[i][j] = max(dp[i][j + 1], dp[i + 1][j]);
            }
        }
        return n + m - dp[0][0];
    }
</pre>
