## Problem of the Day - [<a href="https://leetcode.com/problems/zigzag-conversion/description/"> 6. Zigzag Conversion </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    string convert(string s, int numRows) {
        if(numRows <= 1) return s;
        vector<string>v(numRows, ""); 
        int j = 0, dir = -1;
        for(int i = 0; i < s.length(); i++){
            if(j == numRows - 1 || j == 0) dir *= (-1); 
		    v[j] += s[i];
            if(dir == 1) j++;
            else j--;
        }
        string res;
        for(auto &it : v) res += it; 
        return res;
    }
</pre>
