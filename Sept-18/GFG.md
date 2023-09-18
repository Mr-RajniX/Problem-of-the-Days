### Problem of the Day : [Power of 2](https://practice.geeksforgeeks.org/problems/power-of-2-1587115620/1)

#### Solution :
<pre>
  bool isPowerofTwo(long long n){
        if ( n == 0 ) return false;
        return  ( n & (n-1) ) == 0;
  }
</pre>
