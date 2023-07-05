## Problem of the Day - [ <a href="https://leetcode.com/problems/longest-subarray-of-1s-after-deleting-one-element/"> 1493. Longest Subarray of 1's After Deleting One Element </a>]

### Solution #1 :
<pre>
  int longestSubarray(vector< int >& nums) {
        int n = nums.size();

        int left = 0; 
        int zeros = 0; 
        int ans = 0; 

        for (int right = 0; right < n; right++) { 
            if (nums[right] == 0) {
                zeros++;
            }
            while (left < n && zeros == 2) {
                if (nums[left] == 0) {
                    zeros--;
                }
                left++;
            }
            ans = max(ans, right - left);
        }
        return ans;
    }
</pre>
