### Problem of the Day : [Count number of hops](https://practice.geeksforgeeks.org/problems/count-number-of-hops-1587115620/1)

#### Solution :
<pre>
  long long countWays(int n){
     long long m = 1000000007;
     vector< long long > dp(n+1);
     dp[0] = 1;
     for(int i = 1; i < n+1; i++){
         int a, b, c;
         if( i-1 >= 0) dp[i] += dp[i-1] % m;
         if( i-2 >= 0) dp[i] += dp[i-2] % m;
         if( i-3 >= 0) dp[i] += dp[i-3] % m;
     }return dp[n] % m;
  }
</pre>
