#### Problem of the Day : [1425. Constrained Subsequence Sum](https://leetcode.com/problems/constrained-subsequence-sum/)

#### Solution :
<pre>
  int constrainedSubsetSum(vector<int>& nums, int k) {
        int ans = nums[0];
        deque< int> maxSum;
        for(int i = 0; i < nums.size(); i++){
            nums[i] += !maxSum.empty() ? maxSum.front() : 0;
            ans = max(ans , nums[i]);

            while(!maxSum.empty() && nums[i] > maxSum.back())
                maxSum.pop_back();
          
            if(nums[i] > 0) maxSum.push_back(nums[i]);
          
            if(i >= k && !maxSum.empty() && maxSum.front() == nums[i-k]) 
                maxSum.pop_front();
        } return ans;
    }
</pre>
