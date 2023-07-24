### Problem of the Day : [50. Pow(x, n)](https://leetcode.com/problems/powx-n/)

#### Solution :
<pre>
  double myPow(double x, int n) {
        if(x==1 || n == 0) return 1;
        if(n==1) return x;
        double ans = solve(x, abs(n));
        if(n < 0) return 1/ans;
        return ans;
    }
    double solve(double x, long long t){
        double ans = 1;
        while(t > 0){
            int c = t&1;
            if(c == 1) ans *= x;
            x = x*x;
            t = t >> 1;
        }return ans;
    }
</pre>
#### Solution #2 :
<pre>
    double myPow(double x, int n) {
        return pow(x,n);
    }
</pre>
