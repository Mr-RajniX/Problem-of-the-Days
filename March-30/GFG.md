## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/1ccf56f107bcb24242469ea45c02f852165a2184/1"> Minimum Integer </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int minimumInteger(int n, vector<int> &arr) {
        long long sum = 0;
        for(int i : arr) sum+=i;
        int ans = INT_MAX;
        for(int i : arr) if(sum <= (long long)n*i) ans=min(ans, i);
        
        return ans;
    }
</pre>
