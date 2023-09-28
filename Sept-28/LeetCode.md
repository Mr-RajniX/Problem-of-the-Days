### Problem of the Day : [905. Sort Array By Parity](https://leetcode.com/problems/sort-array-by-parity/description/)

##### Solution :
<pre>
  vector< int> sortArrayByParity(vector< int>& nums) {
        int i = 0, j = nums.size() - 1;        
        while (i < j) {
            while (i < j && nums[i] % 2 == 0)
                i++;
            while (i < j && nums[j] % 2 == 1)
                j--;
            
            swap(nums[i], nums[j]);
        }        
        return nums;
    }
</pre>
