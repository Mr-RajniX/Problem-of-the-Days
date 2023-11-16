#### Problem of the Day : [1980. Find Unique Binary String](https://leetcode.com/problems/find-unique-binary-string/)

#### Solution :
<pre>
  string findDifferentBinaryString(vector< string>& nums) {
        string result;
        for (int i = 0; i < nums.size(); ++i) 
            result += (nums[i][i] == '0' ? '1' : '0');
        return result;
    }
</pre>
