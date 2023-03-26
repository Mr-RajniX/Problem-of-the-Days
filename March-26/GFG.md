## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/5551749efa02ae36b6fdb3034a7810e84bd4c1a4/1"> Frogs and Jumps </a>]


#### ⭐<ins>Solution Function Code</ins> -
    int unvisitedLeaves(int N, int leaves, int frogs[]) {
        vector<bool> seive(leaves+1,false);
        for(int i=0;i<N;i++){
            int temp=frogs[i];
            if(seive[temp]==false){
                for(int j=temp;j<=leaves;j+=temp){
                    seive[j]=true;
                }
            }
        }
        int ans=0;
        for(int i=1;i<=leaves;i++){
            if(seive[i]==false) ans++;
        }
        return ans;
    }

