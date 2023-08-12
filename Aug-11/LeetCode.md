### Problem of the Day : [518. Coin Change II](https://leetcode.com/problems/coin-change-ii/)

#### Solution : 
<pre>
  int change(int amount, vector< int >& coins) {
       vector< int > dp(amount+1, 0);
        dp[0]=1;
        for(int c:coins){
            for(int i=1; i<=amount; i++)
                if (i-c>=0)
                    dp[i]+=dp[i-c];
        }
        return dp[amount]; 
    }
</pre>
