## Problem of the Day : [ <a href="https://leetcode.com/problems/minimum-size-subarray-sum/"> 209. Minimum Size Subarray Sum </a> ]

### Solution #1 :
<pre>
  int minSubArrayLen(int target, vector< int >& nums) {
        int i = 0,j = 0, sum = 0;
        int ans = INT_MAX;
        while(j < nums.size()){
            sum += nums[j];
            while(sum >= target){
                sum -= nums[i];
                ans = min(j-i+1, ans);
                i++;
            }j++;
        }
        if(ans == INT_MAX) return 0;
        return ans;
    }
</pre>
