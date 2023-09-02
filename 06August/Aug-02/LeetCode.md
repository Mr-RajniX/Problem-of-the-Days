### Problem of the Day : [46. Permutations](https://leetcode.com/problems/permutations/)

#### Solution :
<pre>
  void permutation(vector< int >& nums, int begin, vector< vector< int > >& result) { 
            if (begin == nums.size()) { 
                result.push_back(nums); 
                return; 
            } 
        for (int i = begin; i < nums.size(); i++) { 
            swap(nums[begin], nums[i]); 
            permutation(nums, begin + 1, result); 
            swap(nums[begin], nums[i]); 
        } 
    } 
                                                                                                   
    vector< vector< int > > permute(vector< int >& nums) {
        vector< vector< int >> result; 
        permutation(nums, 0, result); 
        return result; 
                             
    }
</pre>
