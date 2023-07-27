### Problem of the Day : [2141. Maximum Running Time of N Computers](https://leetcode.com/problems/maximum-running-time-of-n-computers/)

#### Solution :
<pre>
  long long maxRunTime(int n, vector< int >& batteries) {
        long long low = 1;
        long long high = accumulate(begin(batteries), end(batteries), 0LL) / n;

        while( low < high ){
            long long mid = (high + low + 1 )/2;
            long long time = 0;
            for( int x : batteries ) time += min((long long) x , mid );

            if( mid*n <= time ) low = mid;
            else high = mid - 1;
        }
        return low;
    }
</pre>
