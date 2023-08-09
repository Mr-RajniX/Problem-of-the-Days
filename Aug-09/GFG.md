### Problem of the Day : [Largest prime factor](https://practice.geeksforgeeks.org/problems/largest-prime-factor2601/1)

#### Solution :
<pre>
  long long int largestPrimeFactor(long long int N){
        long long int maxi=0;
        long long int i;
        for( i=2;i*i<=N;i++){
            while(N%i==0){
                maxi=max(maxi,i);
                N=N/i;
            }
        }
        if(N>1){
            maxi=max(maxi,N);
        }
        return maxi;
    }
</pre>
