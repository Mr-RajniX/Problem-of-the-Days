## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/78a6854c8a2915e05f236aa407dfaa1bbc8ae7d3/1"> Equal Left and Right Subarray Sum </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


    int equalSum(int N, vector<int> &A) {
        // code here
        if(N==1) return 1;
        int sum = 0;
        for(auto i:A) sum += i;
        int x = 0;
        for(int i=0; i<N; i++){
            int t = sum-A[i];
            if(t == 2*x) return i+1;
            x += A[i];
        }
        return -1;
    }

