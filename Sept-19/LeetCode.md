### Problem of the Day : [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)

#### Solution :
<pre>
  int findDuplicate(vector<int>& nums) {
        int n =  nums.size();
        for(int i = 0; i < n; i++){
            int digit = abs(nums[i]);
            if( nums[digit] < 0) return digit;

            nums[digit] = -nums[digit];
        }return n;
    }
</pre>
