### Problem of the day - [ <a href="https://leetcode.com/problems/put-marbles-in-bags/"> 2551. Put Marbles in Bags </a> ]

#### Solution :
<pre>
  long long putMarbles(vector< int >& weights, int k) {
        int n = weights.size();
        vector< long long > pairs;
        for(int i=1; i < n; i++){
            pairs.push_back( weights[i] + weights[i-1]);
        }sort(pairs.begin(), pairs.end());
        long long mini = 0, maxi = 0;
        for(int i=0; i < k-1; i++){
            mini += pairs[i];
            maxi += pairs[n-2-i];
        }
        return (maxi - mini);
    }
</pre>
