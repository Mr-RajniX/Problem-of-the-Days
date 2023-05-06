## Problem of the Day - [<a href="https://leetcode.com/problems/number-of-subsequences-that-satisfy-the-given-sum-condition/"> 1498. Number of Subsequences That Satisfy the Given Sum Condition </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int numSubseq(vector<int>& nums, int target) {
        int res = 0, mod = 1000000007, l = 0, r = nums.size() - 1;
        vector<int> pre = {1};
        for (auto i = 1; i <= nums.size(); ++i)
            pre.push_back((pre.back() << 1) % mod);   
                
        sort(begin(nums), end(nums));
        
        while (l <= r) {
            if (nums[l] + nums[r] > target) {
                r--;
            } else {
                res = (res + pre[r - l++]) % mod;
            }
        }

        return res;
    }
</pre>
