## Problem of the Day - [<a href="https://leetcode.com/problems/minimum-insertion-steps-to-make-a-string-palindrome/"> 1312. Minimum Insertion Steps to Make a String Palindrome </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int lcs(string t, string s, vector<vector<int>>&dp){
        int n = s.size();
        for(int i = 0; i <= n; i++){
            for(int j = 0; j <= n; j++){
                if(i == 0 || j == 0)
                dp[i][j] = 0;
            }
        }

        for(int i = 1; i <= n; i++){
            for(int j = 1; j <= n; j++){
                if(s[i-1] == t[j-1]){
                    dp[i][j] = 1 + dp[i-1][j-1];
                } else{
                    dp[i][j] = max(dp[i-1][j],dp[i][j-1]);
                }
            }
        }
        return dp[n][n];
    }
    
    int minInsertions(string s) {
        string t = s;
        reverse(t.begin(),t.end());
        int n = s.size();
        vector<vector<int>>dp(n+1,vector<int>(n+1,0));
        return n - lcs(s,t,dp);
    }
</pre>
