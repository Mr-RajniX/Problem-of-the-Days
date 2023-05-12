## Problem of the Day - [<a href="https://leetcode.com/problems/solving-questions-with-brainpower/"> 2140. Solving Questions With Brainpower </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   long long mostPoints(vector<vector<int>>& questions) {
        int n = questions.size();
        vector<long long> dp(n + 1, 0);
        for (int i = n - 1; i >= 0; --i) {
            int points = questions[i][0];
            int jump = questions[i][1];
            int nextQuestion = min(jump + i + 1, n);
            long long pointsFromThisQuestion = points + dp[nextQuestion];
            dp[i] = max(pointsFromThisQuestion, dp[i + 1]);
        }
        return dp[0];
    }
</pre>
