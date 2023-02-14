## Problem of the Day - [<a href="https://leetcode.com/problems/add-binary/description/"> 67. Add Binary </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    string addBinary(string a, string b) {
        int i=a.length()-1, j=b.length()-1;
        int k = 0;
        string ans = "";
        while(k>0 || i>=0 || j>=0){
            int d = (i>=0 ? (a[i]-'0') : 0) + (j>=0 ? (b[j]-'0') : 0);
            if(d==2 && k==0){
                ans += '0';
                k = 1;
            }
            else if(d==1 && k==0){
                ans += '1';
                k =0;
            }
            else if(d==0 && k==0){
                ans += '0';
                k = 0;
            }
            else if(d==2 && k==1){
                ans += '1';
                k = 1;
            }
            else if(d==1 && k==1){
                ans += '0';
                k = 1;
            }
            else if(d==0 && k==1){
                ans += '1';
                k = 0;
            }
            i--, j--;
        }
        reverse(ans.begin(),ans.end());
        return ans;
    }
</pre>
