### Problem of the Day :[486. Predict the Winner](https://leetcode.com/problems/predict-the-winner/)

#### Solution : 
<pre>
  bool PredictTheWinner(vector<int>& nums) {
        int n = nums.size();
        vector< int > dp(n);

        for(int i = n-1; i >= 0; i--) {
            dp[i] = nums[i];
            for(int j = i + 1; j < n; j++){
                dp[j] = max(nums[i] - dp[j], nums[j] - dp[j-1]);
            }
        }return dp[n-1] >= 0;
    }
</pre>
