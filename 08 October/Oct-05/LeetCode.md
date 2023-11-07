### Problem of the Day : [229. Majority Element II](https://leetcode.com/problems/majority-element-ii/)

#### Solution :
<pre>
  vector< int> majorityElement(vector< int>& nums) {
        vector< int> result;
        int candidate1 = 0, candidate2 = 1, count1 = 0, count2 = 0;

        for (int num : nums) {
            if (num == candidate1) count1++;
            else if (num == candidate2) count2++;
            else if (count1 == 0) candidate1 = num, count1 = 1;
            else if (count2 == 0) candidate2 = num, count2 = 1;
            else count1--, count2--;
        }
        count1 = count2 = 0;
        for (int num : nums) {
            if (num == candidate1) count1++;
            if (num == candidate2) count2++;
        }
        if (count1 > nums.size() / 3) result.push_back(candidate1);
        if (count2 > nums.size() / 3) result.push_back(candidate2);

        return result;
    }
</pre>
