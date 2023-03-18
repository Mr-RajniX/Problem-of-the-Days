## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/6f08220ca3b871be594f50f7f56a9ef2799cb485/1"> Median of the Subarrays </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    long long helper( int n, const vector< int >& a, int m ) {
        vector< int > v( 2 * n + 1 ); v[ n ]++;
        long long x{}, t{}, j{ n };
        for ( int i{}; i < n; ++i, ++v[ j ] )
            x += t += a[ i ] >= m ? v[ j++ ] : -v[ --j ];
        return x;
    }
    long long countSubarray( int N, vector< int > A, int M ) {
        return helper( N, A, M ) - helper( N, A, ++M );
    }
</pre>
