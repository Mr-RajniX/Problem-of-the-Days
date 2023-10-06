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

#### Solution 2:
<pre>
  int integerBreak(int n) {
        if (n <= 3) {
            return n - 1;
        }
        int quotient = n / 3;
        int remainder = n % 3;
        if (remainder == 0) {
            return pow(3, quotient);
        } else if (remainder == 1) {
            return pow(3, quotient - 1) * 4;
        } else {
            return pow(3, quotient) * 2; 
        }
    }
</pre>
