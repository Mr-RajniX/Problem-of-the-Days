#### Problem of the Day : [1759. Count Number of Homogenous Substrings](https://leetcode.com/problems/count-number-of-homogenous-substrings/)

#### Solution :
<pre>
  int countHomogenous(string s) {
        int left = 0;
        long long res = 0;        
        for (int right = 0; right < s.length(); right++) {
            if (s[left] == s[right]) {
                res += right - left + 1;
            } else {
                res += 1;
                left = right;
            }
        } return (int) (res % (1000000007));  
    }
</pre>
