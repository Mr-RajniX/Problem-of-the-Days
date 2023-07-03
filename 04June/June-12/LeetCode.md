## Problem of the Day - [<a href="https://leetcode.com/problems/summary-ranges/"> 228. Summary Ranges </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  vector<string> summaryRanges(vector<int>& nums) {
       vector<string> Res;        
        if(nums.size() < 1)
           return Res;
        
        for(int i=0;i < nums.size();){
            int low=i;
            int high=i;            
            while(high+1 < nums.size() && nums[high+1] == nums[high]+1)
                high++;
            if(high > low)
                Res.push_back(to_string(nums[low]) + "->" + to_string(nums[high]));
            else
                Res.push_back(to_string(nums[high]));
            i=high+1; 
        }          
        return Res;
    }
</pre>
