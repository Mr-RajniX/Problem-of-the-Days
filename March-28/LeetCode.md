## Problem of the Day - [<a href="https://leetcode.com/problems/minimum-cost-for-tickets/description/"> 983. Minimum Cost For Tickets </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int mincostTickets(vector<int>& days, vector<int>& costs) {
        int n = days.size();
        vector<int> dp(366, INT_MAX);
        dp[0] = 0;
        int j = 0;
        for (int i = 1; i <= 365; i++) {
            if (j < n && i == days[j]) {
                dp[i] = min(dp[i], dp[i-1] + costs[0]);
                if (i >= 7) 
                    dp[i] = min(dp[i], dp[i-7] + costs[1]);
                else 
                    dp[i] = min(dp[i], costs[1]);
                if (i >= 30) 
                    dp[i] = min(dp[i], dp[i-30] + costs[2]);
                else 
                    dp[i] = min(dp[i], costs[2]);
                j++;
            } 
            else {
                dp[i] = dp[i-1];
            }
        }
        return dp[365];
    }
</pre>
