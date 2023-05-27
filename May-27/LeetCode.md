## Problem of the Day - [<a href="https://leetcode.com/problems/stone-game-iii/"> 1406. Stone Game III </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  string stoneGameIII(vector<int> &v) {
      const int n = v.size();
      reverse(v.begin(), v.end());
      vector<int> dp(n+1, -1000 * 50000), sum = {0};
      for (auto x : v) sum.push_back(x + sum.back());
      dp[0] = 0;
      for (int i = 0; i < n; i++) {
        dp[i + 1] = max(dp[i + 1], v[i] + sum[i] - dp[i]);
        if (i > 0) dp[i + 1] = max(dp[i + 1], v[i] + v[i - 1] + sum[i - 1] - dp[i - 1]);
        if (i > 1) dp[i + 1] = max(dp[i + 1], v[i] + v[i - 1] + v[i - 2] + sum[i - 2] - dp[i - 2]);
      }
      if (dp[n] * 2 == sum[n]) return "Tie";
      else if (dp[n] * 2 > sum[n]) return "Alice";
      else return "Bob";
    }
</pre>
