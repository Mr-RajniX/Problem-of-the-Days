## Problem of the Day - [<a href="https://leetcode.com/problems/new-21-game/"> 837. New 21 Game </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  double dp[10001];
    double new21Game(int n, int k, int maxPts) {
        if (!k) return 1;
        double ans = 0, cur = 1.0 / maxPts;
        dp[0] = 1;
        for (int i = 1; i <= n; ++i) {
            dp[i] = cur;
            if (i >= k) ans += dp[i];
            else cur += dp[i] / maxPts;
            if (i >= maxPts && dp[i]) cur -= dp[i-maxPts] / maxPts;
        }
        return ans;
    }
</pre>
#### ⭐<ins>Solution Function Code #2</ins> -
<pre>

  double new21Game(int n, int k, int maxPts) {
        if (k == 0 || n >= k + maxPts) {
            return 1.0;
        }
        vector<double> dp(n + 1);
        double currSum = 1.0;
        double ans = 0.0;
         dp[0] = 1.0;
        for (int i = 1; i < n+1; i++) {
            dp[i] = currSum / maxPts;
            if (i < k) 
                currSum += dp[i];
            else 
                ans += dp[i];            
            if (i - maxPts >= 0) 
                currSum -= dp[i - maxPts];   
        }
        return ans;
    }
</pre>

