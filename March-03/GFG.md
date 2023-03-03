## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/a7a4da81b20f4a05bbd93f5786fcf7478298f4f5/1"> Cutting Rectangles </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    vector<long long int> minimumSquares(long long int L, long long int B){
        // code here
        vector<long long int> v;
        long long K = __gcd(L,B);
        long long N = (L*B)/(K*K);        
        v.push_back(N);
        v.push_back(K);
        return v;
    }
</pre>
