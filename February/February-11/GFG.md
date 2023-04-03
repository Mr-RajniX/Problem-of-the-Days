## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/f4d22b1f9d62e8bee0ff84e9fa51dc66eb5005ec/1"> Minimum Days </a>]


#### ⭐<ins>Solution Function Code</ins> -


    int getMinimumDays(int N,string S, vector<int> &P) {
        // code here
        int ans=0;
        for(int i=0;i<N;i++) {
            int idx = P[i];
            if(idx==0) {
                if(idx+1<N && S[idx]==S[idx+1]) {
                    S[idx]='?';
                    ans = i+1;
                }
            } else if(idx==N-1) {
                if(idx-1>=0 && S[idx]==S[idx-1]) {
                    S[idx]='?';
                    ans = i+1;
                }
            } else {
                if(S[idx]==S[idx-1] || S[idx]==S[idx+1]) {
                    S[idx]='?';
                    ans = i+1;
                }
            }
        }
        return ans;
    }

