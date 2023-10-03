### Problem of the Day : [1512. Number of Good Pairs](https://leetcode.com/problems/number-of-good-pairs/)

#### Solution :
<pre>
  int numIdenticalPairs(vector< int>& nums) {
        int ans = 0;
        unordered_map< int, int> cnt;
        for (int x: nums) ans += cnt[x]++;
        return ans;
    }
</pre>
