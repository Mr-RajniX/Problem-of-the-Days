### Problem of the Day : [Power Of Numbers](https://practice.geeksforgeeks.org/problems/power-of-numbers-1587115620/1)

#### Solution :
<pre>
  long long power(int N,int R){
        long long res = 1; 
        long long int mod = 1000000007; 
        while (R > 0) {
            if (R & 1)
                res = (res * N)%mod;     
            R = R >> 1; 
            N = (N * (N%mod))%mod;
        }        
        return res;
    }
</pre>
