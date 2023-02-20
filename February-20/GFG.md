## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/aa0000a5f710ce8d41366b714341eef644ec7b82/1"> Count Cyclic Paths </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    long long int mod=1e9+7;
    int countPaths(int n){
        if(n==1){
            return 0;
        }
        if(n==2){
            return 3;
        }
        if(n==3){
            return 6;
        }
        if(n==4){
            return 21;
        }
        vector<long long int> dp(n+1,0);
        dp[1]=0;
        dp[2]=3;
        dp[3]=6;
        dp[4]=21;
        for(long int i=5;i<=n;i++){
            dp[i]=((2*dp[i-1])%mod+(dp[i-2]*dp[2])%mod)%mod;
        }
        return dp[n];
    }
</pre>
