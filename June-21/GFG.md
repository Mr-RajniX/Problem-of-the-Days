## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/reverse-coding2452/1"> Reverse Coding </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int sumOfNaturals(int n) {
        int mod = 1000000007;
        long long sum = ( (n%mod) * 1L * ((n+1)%mod )) / 2;
        return int(sum % mod);
    }
</pre>
