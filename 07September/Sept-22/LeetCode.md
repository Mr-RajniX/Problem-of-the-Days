### Problem of the Day : [392. Is Subsequence](https://leetcode.com/problems/is-subsequence/)

#### Solution :
<pre>
  bool isSubsequence(string s, string t) {
        int j = 0;
        int n = s.length(),m=t.length();
        for ( int i = 0; i < m & j < n; i++){
            if( s[j] == t[i]) j++;
        } return (j == n);
    }
</pre>
