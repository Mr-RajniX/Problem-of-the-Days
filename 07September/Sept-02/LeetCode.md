### Problem of the Day : [2707. Extra Characters in a String](https://leetcode.com/problems/extra-characters-in-a-string/)

#### Solution :
<pre>
  int minExtraChar(string s, vector< string >& dictionary) {
       int dp[51] = {}; 
        int n = s.size();        
        for (int i = n - 1; i >= 0; --i) {
            dp[i] = 1 + dp[i + 1];             
            for (const auto &w : dictionary) {
                if (i + w.size() <= n && s.compare(i, w.size(), w) == 0) {
                    dp[i] = min(dp[i], dp[i + w.size()]); 
                }
            }
        }        
        return dp[0]; 
    }
</pre>
