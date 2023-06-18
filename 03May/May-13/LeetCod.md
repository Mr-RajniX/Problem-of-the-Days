## Problem of the Day - [<a href="https://leetcode.com/problems/count-ways-to-build-good-strings/"> 2466. Count Ways To Build Good Strings </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int countGoodStrings(int low, int high, int zero, int one) {
         int dp[high+1];
    memset(dp, 0, sizeof(dp));
    dp[0]=1;
    int ans=0;
    for(int i=1;i<=high;i++){
        dp[i] = ((i-zero>=0 ? dp[i-zero]:0)+(i-one>=0 ? dp[i-one]:0))%1000000007;
        if(i>=low){
            ans = (ans+dp[i])%1000000007;
        }
    }
    return ans;
    }
</pre>
