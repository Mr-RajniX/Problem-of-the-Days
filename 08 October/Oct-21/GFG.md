#### Problem of the Day : [Sum of all divisors from 1 to n](https://practice.geeksforgeeks.org/problems/sum-of-all-divisors-from-1-to-n4738/1)

#### Solution :
<pre>
  long long sumOfDivisors(int N){
        long long ans = N;
        for(int i = 2; i <= N; i++){
            int iOccur = N / i;
            ans += (1ll * iOccur * i);
        } return ans;
    }
</pre>
