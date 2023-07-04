## Problem of the Day - [ <a href="https://practice.geeksforgeeks.org/problems/count-the-subarrays-having-product-less-than-k1708/1">Count the subarrays having product less than k</a>]

### Solution #1 :
<pre>
  int countSubArrayProductLessThanK(const vector< int >& nums, int n, long long k) {
        long long left = 0, right = 0, prod = 1, count = 0;
        while (right < n) {
            prod *= nums[right];
            while (left <= right && prod >= k) {
                prod /= nums[left];
                left++;
            }
            count += (right - left + 1);
            right++;
        }
        return count;

    }
</pre>
