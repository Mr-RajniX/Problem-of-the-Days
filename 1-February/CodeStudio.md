## Problem of the Day - [<a href="https://www.codingninjas.com/codestudio/problems/meta-strings_1089556">Code Studio</a>]


#### ⭐<ins>Solution Codes</ins> -
<pre>
  ⭐Level : EASY - <a href="https://www.codingninjas.com/codestudio/problems/meta-strings_1089556">Meta Strings</a>
    bool checkMeta(string &s1, string &s2)
    {
        int s1_len = s1.length();
        int s2_len = s2.length();
        if (s1_len != s2_len)
        return false;
        int prev = -1, curr = -1;
        int count = 0;
        for (int i=0; i<s1_len; i++) {
            if (s1[i] != s2[i]) {
                count++; 
                if (count > 2)
                return false;
                prev = curr;
                curr = i;
            }
        }
        return (count == 2 && s1[prev] == s2[curr] && s1[curr] == s2[prev]);
    }
</pre>
