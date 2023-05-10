## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/cbd515a00f6537180d2e66f1ffe11093a128e560/1"> Total Cuts </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int totalCuts(int N,int K,vector<int> &A){
        // Code here
        vector<int> pref(N, 0);
        pref[N-1] = A[N-1];
        for(int i = N-2; i>=0 ; i--){
            pref[i] = min(pref[i+1],A[i]);
        }
        int maxi = A[0];
        int ans = 0;
        for(int i = 1; i < N; i++){
            if(maxi + pref[i] >= K)
                ans++;
            maxi = max(maxi, A[i]);
        }
        return ans;
    }
</pre>
