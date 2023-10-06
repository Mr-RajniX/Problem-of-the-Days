### Problem of the Day : [343. Integer Break](https://leetcode.com/problems/integer-break/)

#### Solution :
<pre>
  int integerBreak(int n) {
        if(n <= 3) return n-1;
        int ans  = 1;
        while(n > 4){
            ans *= 3;
            n -= 3;
        }return ans*n;
    }
</pre>
