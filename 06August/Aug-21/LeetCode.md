### Problem of the Day : [459. Repeated Substring Pattern](https://leetcode.com/problems/repeated-substring-pattern/)

#### Solution :
<pre>
  bool repeatedSubstringPattern(string s) {
        int n = s.size();
        for(int i = n - 1; i >= 1; i--)
            if(n % i == 0)
                if(s.substr(0, n - i) == s.substr(i))
                    return true;
        return false;
    }
</pre>
