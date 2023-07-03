## Problem of the Day - [<a href="https://leetcode.com/problems/k-radius-subarray-averages/"> 2090. K Radius Subarray Averages </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  vector< int > getAverages(vector< int >& nums, int k) {
        int n = nums.size();
        int winSize = 2 * k + 1;
        vector< int > ans(n, -1);

        if (n < winSize) {
            return ans;
        }
        vector < long long > preSum(n + 1);
        for (int i = 0; i < n; ++i) {
            preSum[i + 1] = preSum[i] + nums[i];
        }
        for (int i = k ; i + k < n; ++i) {
            ans[i] = (preSum[i + k + 1] - preSum[i - k]) / winSize;
        }
        return ans;
    }
</pre>
