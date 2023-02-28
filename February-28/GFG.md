## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/d4aeef538e6dd3280dda5f8ed7964727fdc7075f/1"> Optimal Array </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    vector<int> optimalArray(int n,vector<int> &a){
        // Code here
        vector<int>ans(n,0);
        int i=1;
        while(i<n){
            ans[i] = ans[i-1] + (a[i] - a[i/2]);
            i++;
        }
        return ans;
    }
</pre>
