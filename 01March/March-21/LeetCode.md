## Problem of the Day - [<a href="https://leetcode.com/problems/number-of-zero-filled-subarrays/description/"> 2348. Number of Zero-Filled Subarrays </a>]


#### ⭐<ins>Solution Function Code</ins> -


    long long zeroFilledSubarray(vector<int>& nums) {
        long long contCount = 0;
        long long subarrays = 0;
        for(int i=0; i<nums.size(); i++){
            if(nums[i]==0){
                contCount++;
                subarrays += contCount;
            }
            else{
                contCount=0;
            }
        }
        return subarrays;
    }

