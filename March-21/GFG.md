## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/7995e41d167d81f14f1d4194b29ef839f52d18ba/1"> Taxi Booking </a>]


#### ⭐<ins>Solution Function Code</ins> -

    int minimumTime(int N,int cur,vector<int> &pos,vector<int> &time){
        int ans = INT_MAX;
        for(int i=0; i<N; i++){
            int s = (pos[i] - cur) * time[i];
            if (s<0) s=s*(-1);
            if(s<ans) ans=s;
        }
        return ans;
    }
