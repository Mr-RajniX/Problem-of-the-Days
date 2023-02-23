## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/51afa710a708c0681748445b509696dd588d5c40/1"> Largest Sum Cycle </a>]


#### ⭐<ins>Solution Function Code</ins> -


    long long largestSumCycle(int N, vector<int> Edge){
    // code here
    vector<long long> psum(N, -1), visited(N, -1);
        long long res = -1;
        for (long long i=0; i<N; i++) {
            if (visited[i] == -1) {
                visited[i] = i;
                psum[i] = i;
                long long j = i;
                while (Edge[j] != -1) {
                    if (visited[Edge[j]] == -1) {
                        visited[Edge[j]] = i;
                        psum[Edge[j]] = psum[j] + Edge[j];
                        j = Edge[j];
                    }
                    else {
                        if (visited[Edge[j]] == i) {
                            res = max(res, psum[j] - psum[Edge[j]] + Edge[j]);
                        }
                        break;
                    }
                }
            }
        }
        return res;
    }

