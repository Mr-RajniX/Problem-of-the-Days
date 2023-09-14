### Problem of the Day : [Perfect Sum Problem](https://practice.geeksforgeeks.org/problems/perfect-sum-problem5633/1)

#### Solution :
<pre>
  int perfectSum(int arr[], int n, int sum){
        const int MOD = 1e9 + 7;
        vector< vector< int >> dp(n + 1, vector< int >(sum + 1, 0));
        
        dp[0][0] = 1;
        for (int j = 1; j <= sum; j++)
            dp[0][j] = 0;
        
        for (int i = 1; i <= n; i++) {
            for (int j = 0; j <= sum; j++) {
                if (arr[i - 1] <= j)
                    dp[i][j] = (dp[i - 1][j] + dp[i - 1][j - arr[i - 1]]) % MOD;
                else
                    dp[i][j] = dp[i - 1][j];
            }
        }
        return dp[n][sum];
  }
</pre>
