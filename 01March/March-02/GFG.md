## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/9dacc32ad062be6e2ba8f6c41aad0b2b2376397d/1"> Walls Coloring II </a>]


#### ⭐<ins>Solution Function Code</ins> -


    int minCost(vector<vector<int>> &costs) {
        // write your code here
        int n = costs.size(), k = costs[0].size();
        if(k==1 and n!= 1){
            return -1;
        }
        vector<vector<int>> dp(n, vector<int>(k, 0));
        set<pair<int,int>> st;
        for (int i = 0; i < k; i++){
            dp[0][i] = costs[0][i];
            st.insert({dp[0][i],i});
        }
        for (int i = 1; i < n; i++){
            for (int j = 0; j < k; j++){
                dp[i][j] = costs[i][j];
                auto it = st.begin();
                auto p = *it;
                if(p.second != j){
                    dp[i][j]+=p.first;
                }
                else if(st.size()>1){
                    it++;
                    auto yp = *it;
                    dp[i][j]+=yp.first;
                }
            }
            st.clear();
            for(int j = 0;j<k;j++){
                st.insert({dp[i][j],j});
            }
        }
        int a = 1e9;
        for(int i = 0;i<k;i++){
          a = min(a,dp[n-1][i]);
        }
        if(a==1e9){
          return -1;
        }
        return a;
    }
