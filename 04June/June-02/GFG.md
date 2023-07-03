## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/santa-banta2814/1"> Santa Banta </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  vector<int>dp;
    void precompute(){
        dp.resize(1e6+1,1);
        for(int i = 2; i <= 1e6; i++){
            if(dp[i])
            for(int  j = 2*i; j<=1e6; j += i){
                dp[j] = 0; 
            }
        }
    }
    
    void dfs(vector<vector<int>>&adj, vector<int>&vis, int node, int &cnt){
        cnt++;
        vis[node] = 1;
        for(auto it: adj[node]){
            if(!vis[it]){
                dfs(adj, vis, it, cnt);
            }
        }
    }
    int helpSanta(int n, int m, vector<vector<int>> &g){
        int ans = 0;
        vector<int>vis(n+1, 0);
        for(int i =1; i <= n; i++){
            int cnt =0;
            if(!vis[i]){
                dfs(g, vis, i, cnt);
            }
            ans = max(ans, cnt);
        }
        if(ans==1)return -1;
        int cnt = 0;
        for(int i = 2; i <= 1e6; i++){
            if(dp[i])cnt++;
            if(cnt==ans)return i;
        }
        return -1;     
    }
</pre>
