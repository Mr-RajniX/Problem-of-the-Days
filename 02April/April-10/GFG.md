## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/63c232252d445a377e01cd91adfd7d1060580038/1"> Maximum Intersecting Lines </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


    int maxIntersections(vector<vector<int>> l, int n) {
        map<int,int> m;        
        for(int i=0;i<n;i++){
            m[l[i][0]] += 1;
            m[l[i][1]+1] -= 1;
        }
        int c=0,pre_sum=0;
        for(auto x: m){
            pre_sum += x.second;
            c = max(c,pre_sum);
        }
        return c;
    }
