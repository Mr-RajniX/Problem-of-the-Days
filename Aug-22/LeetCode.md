### Problem of the day : [168. Excel Sheet Column Title](https://leetcode.com/problems/excel-sheet-column-title/)

#### Solution : 
<pre>
  string convertToTitle(int n) {
        if( n < 26) return string(1, 'A' + (n-1) % 26);
        string ans =  "";
        while(n){
            n--;
            char c = 'A' + n % 26;
            ans = c + ans;
            n /= 26;
        } 
        return ans;
    }
</pre>
