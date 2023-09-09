### Problem of the Day : [377. Combination Sum IV](https://leetcode.com/problems/combination-sum-iv/)

#### Solution :
<pre>
  int combinationSum4(vector< int >& nums, int target) {
        vector< unsigned long long > dp(target + 1, 0);
        dp[0] = 1;
        for(int currentSum = 1; currentSum <= target; currentSum++) {
            for(int numIndex = 0; numIndex < nums.size(); numIndex++) {
                int currentNum = nums[numIndex];
                if(currentSum - currentNum >= 0) {
                    dp[currentSum] += dp[currentSum - currentNum];
                }
            }
        }        
        return dp[target];
    }
</pre>
