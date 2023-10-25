#### Problem of the Day : [Knapsack with Duplicate Items](https://practice.geeksforgeeks.org/problems/knapsack-with-duplicate-items4201/1)

#### Solution :
<pre>
  int knapSack(int N, int W, int val[], int wt[]){
        int dp[W+1] = {0};
        for(int i=0; i < N; i++){
            for(int j=1; j <= W; j++){
                if(j >= wt[i]) dp[j] = max( dp[j], dp[j-wt[i]]+val[i]);
            }
        }return dp[W];
    }
</pre>
