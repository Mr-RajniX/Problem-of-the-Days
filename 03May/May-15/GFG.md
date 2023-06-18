## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/1132bd8ee92072cd31441858402641d6800fa6b3/1"> Count Total Setbits </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   long long countBits(long long N) {
        long long int ans=0;
        for(int i=0;i<=N;i++){
            ans=ans+__builtin_popcount(i);
        }
        return ans;
    }
</pre>
