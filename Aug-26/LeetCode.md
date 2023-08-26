### Problem of the day : [646. Maximum Length of Pair Chain](https://leetcode.com/problems/maximum-length-of-pair-chain/)

#### Solution :
<pre>
  int findLongestChain(vector < vector< int >>& pairs) {
        sort(pairs.begin(), pairs.end(), [](const vector< int>& a, const vector< int>& b) {
            return a[1] < b[1];
        });
        
        int cur = INT_MIN, ans = 0;
        
        for (const auto& pair : pairs) {
            if (cur < pair[0]) {
                cur = pair[1];
                ans++;
            }
        }
        
        return ans;
    }
</pre>
