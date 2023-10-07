### Problem of the Day : [Perfect Numbers](https://practice.geeksforgeeks.org/problems/perfect-numbers3207/1)

#### Solution :
<pre>
  int isPerfectNumber(long long n) {
        long long sum  = 1 ;
        if(n==1) return 0;
        for(long long i=2; i <= sqrt(n); i++){
            if(n % i == 0) {
              sum+=i;
              sum += n/i;
          }
        }if(sum == n) 
            return 1;
        return 0;
    }
</pre>
