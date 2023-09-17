### Problem of the Day : [Print first n Fibonacci Numbers](https://practice.geeksforgeeks.org/problems/print-first-n-fibonacci-numbers1002/1)

#### Solution :
<pre>
  vector< long long> printFibb(int n) {
        if( n == 1 ) return {1};
        vector< long long> v(n,0);
        v[0] = 1;
        v[1] = 1;
        for(int i = 2; i < n; i++) v[i] = v[i-1] + v[i-2];
        return v;
    }
</pre>
