### Problem of the Day : [Nth Fibonacci Number](https://practice.geeksforgeeks.org/problems/nth-fibonacci-number1335/1)

#### Solution : 
<pre>
  int nthFibonacci(int n){
        // code here
        if(n == 0)
            return 0;
        if(n == 1)
            return 1;
        long long int mod = 1000000007;
        long long int ans = 0;
        long long int sec = 1;
        long long int first = 0;
        for(int i=2; i <= n; i++){
            ans = (first+sec)%mod;
            first = sec;
            sec = ans;
        }
        return ans;
    }
</pre>
