## Problem of the Day - [<a href="https://leetcode.com/problems/minimum-cost-to-make-array-equal/"> 2448. Minimum Cost to Make Array Equal </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  long long helper(vector< int >& nums, vector< int >& cost, int all) {
        long long totalCost = 0LL;
        for (int i = 0; i < nums.size(); i++) {
            totalCost += 1LL * abs(nums[i] - all) * cost[i];
        }
        return totalCost;
    }

    long long minCost(vector< int >& nums, vector< int >& cost) {
        int left = nums[0];
        int right = nums[0];
        for (int i : nums) {
            left = min(left, i);
            right = max(right, i);
        }
        long long ans = 0;
        while (left < right) {
            int mid = (left + right) / 2;
            long long cost1 = helper(nums, cost, mid);
            long long cost2 = helper(nums, cost, mid + 1);
            if (cost1 > cost2) {
                left = mid + 1;
                ans = cost2;
            } else {
                right = mid;
                ans = cost1;
            }
        }
        return ans;
    }
</pre>
