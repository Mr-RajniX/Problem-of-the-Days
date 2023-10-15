#### Problem of the Day : [1269. Number of Ways to Stay in the Same Place After Some Steps](https://leetcode.com/problems/number-of-ways-to-stay-in-the-same-place-after-some-steps/)

#### Solution :
<pre>
  int numWays(int steps, int arrLen) {
        const int MOD = 1000000007;

        int max_index = min(steps / 2, arrLen - 1);

        vector< vector< int>> dp(2, vector< int>(max_index + 1, 0));
        dp[0][0] = 1;

        for (int step = 1; step <= steps; ++step) {
            int current = step % 2;
            int prev = (step - 1) % 2;

            for (int index = 0; index <= max_index; ++index) {
                dp[current][index] = dp[prev][index] % MOD;

                if (index > 0) {
                    dp[current][index] = (dp[current][index] + dp[prev][index - 1]) % MOD;
                }

                if (index < max_index) {
                    dp[current][index] = (dp[current][index] + dp[prev][index + 1]) % MOD;
                }
            }
        }

        return dp[steps % 2][0];
    }
</pre>
