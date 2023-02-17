## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/202d95ecdeec659401edc63dd952b1d37b989ab8/1"> Is it Fibonacci? </a>]


#### ⭐<ins>Solution Function Code</ins> -

    long long solve(int N, int K, vector<long long> G) {
        // code here
        int i;
        long long sum=0;
        for( i=0;i<G.size();i++){
           sum+=G[i];
        }
        G.push_back(sum);
       for(i=K+1;i<N;i++){
           long long temp=G[i-1]+(G[i-1]-G[i-1-K]);
           G.push_back(temp);
           temp=0;
       }
       return G[N-1];
    }

