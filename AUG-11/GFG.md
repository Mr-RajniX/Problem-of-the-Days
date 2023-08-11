### Problem of the Day : [Coin Change](https://practice.geeksforgeeks.org/problems/coin-change2448/1)

#### Solution :
<pre>
  long long int count(int coins[], int N, int sum) {
        if(sum == 0) return 1;
        vector< long long >dp(sum+1,0);
        dp[0] = 1;
        for (int i = 0; i < N; ++i) {
            for (int j = coins[i]; j <= sum; ++j) {
                dp[j] += dp[j - coins[i]];
            }
        }
        return dp[sum];
    }
</pre>
