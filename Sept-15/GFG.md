### Problem of the Day : [Partition Equal Subset Sum](https://practice.geeksforgeeks.org/problems/subset-sum-problem2014/1)

#### Solution :
<pre>
  int equalPartition(int n, int arr[]){
        long int sum = 0;
        for(int i = 0 ; i< n; i++) sum += arr[i];
        if(sum & 1) return 0;
        sum /= 2;
        vector< int > dp(sum+1 , 0);
        dp[0] = 1;
        for(int i = 0; i< n; i++){
            for(int j = sum; j >= arr[i] ;j--){
                dp[j] = (dp[j-arr[i]] || dp[j]);
            }
            if(dp[sum]) return 1;
        }
        return 0;
    }
</pre>
