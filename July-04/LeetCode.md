## Problem of the day - <a href="https://leetcode.com/problems/single-number-ii/">137. Single Number II</a>

### Solution #1 :
<pre>
  int singleNumber(vector< int >& nums) {
        int ans = 0, n = nums.size()-1;
        for(int i=0; i<32 ; i++){
            int sum = 0;
            for(const int bit : nums)
                sum += bit >> i & 1;
            sum %= 3;
            ans |= sum << i;
        }
        return ans;
    }
</pre>

### Solution #2 :
<pre>
  int singleNumber(vector< int >& nums) {
        int one = 0 , twice = 0;
        for(const int bit : nums){
            one ^= (bit & ~twice);
            twice ^= (bit & ~one);
        }
        return one;
    }
</pre>
