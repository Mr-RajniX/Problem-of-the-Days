### Problem of the day : [62. Unique Paths](https://leetcode.com/problems/unique-paths/description/)

#### Solution :
<pre>
  int uniquePaths(int m, int n) {
        int r = n -1 ;
        n = m+n-2;
        long long p=1, k=1;
        if (n-r < r)
            r=n-r;
        if(r!=0) {
            while(r) {
                p*=n;
                k*=r;
                long long m=__gcd(p,k);
                p/=m;
                k/=m;
                n--;
                r--;
            }
        }
        else
            p=1;
        return p;
    }
</pre>
