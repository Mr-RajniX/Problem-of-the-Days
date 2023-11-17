#### Problem of the Day : [1877. Minimize Maximum Pair Sum in Array](https://leetcode.com/problems/minimize-maximum-pair-sum-in-array/)

#### Solution :
<pre>
  int minPairSum(vector< int>& nums) {
        int max = INT_MIN;
        int min = INT_MAX;
        int hash[100001] = {0};
        for (int num : nums) {
            hash[num]++;
            max = std::max(max, num);
            min = std::min(min, num);
        }
        int low = min;
        int high = max;
        max = INT_MIN;
        while (low <= high) {
            if (hash[low] == 0) low++;
            else if (hash[high] == 0) high--;
            else {
                max = std::max(max, low + high);
                hash[low]--;
                hash[high]--;
            }
        }return max;
    }
</pre>
