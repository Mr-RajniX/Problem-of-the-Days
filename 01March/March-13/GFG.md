## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/2d3fc3651507fc0c6bd1fa43861e0d1c43d4b8a1/1"> Maximum Possible Value </a>]


#### ⭐<ins>Solution Function Code</ins> -


    long long maxPossibleValue(int n,vector<int> a, vector<int> b) {
        long long ans=0;
        int cnt=0,mini=INT_MAX;
        for(int i=0;i<n;i++){
            int k=b[i]/2;
            cnt+=k;
            ans+=k*a[i]*2;
            if(k>0)mini=min(mini,2*a[i]);
        }
        if(cnt%2)ans-=mini;
        return ans;
    }
