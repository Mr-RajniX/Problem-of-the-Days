### Problem of the Day : [Column name from a given column number](https://practice.geeksforgeeks.org/problems/column-name-from-a-given-column-number4244/1)

#### Solution :
<pre>
  string colName (long long int n){
        string ans;
        while (n > 0) {
            int r = (n - 1) % 26;
            ans = static_cast<char>('A' + r) + ans;
            n = (n - 1) / 26;
        }
        return ans;
    }
</pre>
