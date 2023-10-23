#### Problem of the Day : [342. Power of Four](https://leetcode.com/problems/power-of-four/description/)

#### Solution #1:
<pre>
  bool isPowerOfFour(int n) {
        for(int i = 0; i <= 15; i++){
            int powerValue = pow(4,i);
            if( powerValue == n) return true;
            if( powerValue > n) return false;
        }return false;
    }
</pre>
#### Solution #2:
<pre>
  bool isPowerOfFour(int n) {
        if( n==1 ) return true;
        if( n <= 0) return false;
        double sqroot = sqrt(n);
        double logSq = log2(sqroot);
        return ( logSq == (int)logSq);
    }
</pre>
