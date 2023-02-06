## Problem of the Day - [<a href="https://leetcode.com/problems/shuffle-the-array/description/"> 1470. Shuffle the Array </a>]


#### ⭐<ins>Solution Function Code</ins> -


    vector<int> shuffle(vector<int>& nums, int n) {
        vector<int> ans;
        for(int i=0; i<n; i++){
            ans.push_back(nums[i]);
            ans.push_back(nums[i+n]);
        }
        return ans;
    }

