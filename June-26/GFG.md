## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/ncr1019/1"> nCr </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int nCr(int n, int r){
        if (r > n)
            return 0;
        vector< int > prev(r+1),curr(r+1);
        prev[0] = curr[0] = 1;
        if(r == n || r == 0){
            return 1;
        }
        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= r; j++)
            {
                curr[j] = (prev[j - 1] + prev[j])%mod;
            }
            prev = curr;
        }
        return prev[r];
    }
</pre>
