## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/e047b92794316450814b29de56cc9c6ec18371b7/1"> Maximum subset sum </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     long long findMaxSubsetSum(int N, vector<int> &A) {
          // code here
          long long ans = 0;
          vector<pair<long long,long long>> dp(N,{0,0});
          dp[0].first = A[0];
          dp[0].second = 0;
          for(int i = 1; i<N; i++){
              dp[i].first = max(dp[i-1].first,dp[i-1].second)+A[i];
              dp[i].second = dp[i-1].first;
          }
          return max(dp[N-1].first,dp[N-1].second);
      }
