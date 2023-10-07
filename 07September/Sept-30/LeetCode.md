### Problem of the Day : [456. 132 Pattern](https://leetcode.com/problems/132-pattern/)

##### Solution :
<pre>
  bool find132pattern(vector< int> & nums) {
        stack< int> s;
        int third = INT_MIN;

        for (int i = nums.size() - 1; i >= 0; i--) {
            if (nums[i] < third) return true;
            while (!s.empty() && s.top() < nums[i]) {
                third = s.top();
                s.pop();
            }
            s.push(nums[i]);
        }
        return false;
    }
</pre>
