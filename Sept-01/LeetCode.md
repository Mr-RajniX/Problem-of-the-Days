### Problem of the Day : [338. Counting Bits](https://leetcode.com/problems/counting-bits/)

#### Solution :
<pre>
  vector< int> countBits(int n) {        
        vector< int> t(n+1);        
        t[0] = 0;    
        for(int i = 1; i<=n; ++i)
            t[i] = t[i/2] + i%2;
        return t;
    }
</pre>
