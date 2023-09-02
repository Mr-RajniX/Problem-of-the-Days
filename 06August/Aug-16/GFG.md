### Problem of the Day {`Kyō no mondai`} : [Nth catalan number](https://practice.geeksforgeeks.org/problems/nth-catalan-number0817/1)

#### Solution {`Kaiketsu`}:
<pre>
  int findCatalan(int n) {
        int mod = (int) 1e9 + 7;
        vector < int > dp(n+1);
        dp[0] = dp[1] = 1;
        for (int i = 2; i <= n; i++)
            for(int j= 0; j < i; j++)
                dp[i] = ( dp[i] + ( dp[j] * 1LL * dp[ i - j - 1]) % mod ) % mod;
        return dp[n] % mod;
    }
</pre>
