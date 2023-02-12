## Problem of the Day - [<a href="https://www.codingninjas.com/codestudio/problems/mirror-string_1104722">Code Studio</a>]


#### ⭐<ins>Solution Codes</ins> -
<pre>
  ⭐Level : EASY - <a href="https://www.codingninjas.com/codestudio/problems/mirror-string_1104722">Mirror String</a>
    bool isReflectionEqual(string &s)
    {
      // Write your code here.
      unordered_set<char> symmetric = { 'A', 'H', 'I', 'M',
                            'O', 'T', 'U', 'V', 'W', 'X', 'Y' };
      string s1="";

      for(int i=s.length()-1;i>=0; i--){
        s1=s1+s[i];
        if (symmetric.find(s[i]) == symmetric.end())
                return false;
      }
      if(s1==s) return true;
      return false;
    }
</pre>
