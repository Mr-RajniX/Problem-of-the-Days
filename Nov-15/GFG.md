#### Problem of the Day : [Better String](https://www.geeksforgeeks.org/problems/better-string/1)

#### Solution :
<pre>
  string betterString(string s1, string s2) {
        return getCnt(s2) > getCnt(s1) ? s2 : s1;
    }
    int getCnt(string s) {
        unordered_map< char, int> m;
        int cnt{1}, x;
        for(char c : s) {
            x = 2 * cnt;
            if(m[c]) x -= m[c];
            m[c] = cnt;
            cnt = x;
        }
        return cnt;
    }
</pre>
