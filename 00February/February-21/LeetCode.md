## Problem of the Day - [<a href="https://leetcode.com/problems/single-element-in-a-sorted-array/description/"> 540. Single Element in a Sorted Array </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int singleNonDuplicate(vector<int>& nums) {
        int n = nums.size();
        int low = 0, high = n-1;
        if(nums.size() == 1)
            return nums[0];

        if(nums[0] != nums[1]) return nums[0]; 

        if(nums[n-1] != nums[n-2])   return nums[n-1]; 

        while(low <= high) {
            int mid = low + (high - low)/2;
            if(nums[mid] != nums[mid+1] && nums[mid] != nums[mid-1])
                return nums[mid];
            if(mid % 2 == 0) {
                if(nums[mid] == nums[mid-1]) high = mid-1;
                if(nums[mid] == nums[mid+1]) low = mid+1;
            }
            else if(mid % 2 != 0) {
                if(nums[mid] == nums[mid+1])   high = mid-1;
                if(nums[mid] == nums[mid-1])   low = mid+1;
            }
        }
        return -1;
    }
</pre>
