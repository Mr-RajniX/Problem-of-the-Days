## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/1a4b617b70f0142a5c2b454e6fbe1b9a69ce7861/1"> Number of Good Components </a>]


#### ⭐<ins>Solution Function Code</ins> -


    void dfs(int i, vector<vector<int>> &ar, vector<int> &vis, vector<int> &comp)
    {
        if(vis[i] == 1) return;
        vis[i] = 1;
        comp.push_back(i);
        for(auto it: ar[i]) dfs(it, ar, vis, comp);
        
    }
  
    int findNumberOfGoodComponent(int V, vector<vector<int>>& adj) {
        vector<int> vis(V+2, 0);
        int ans = 0;
        for(int i = 1; i<=V; ++i)
        {
            if(vis[i]==1) continue;
            vector<int> comp;
            dfs(i, adj, vis, comp);
            int sz = comp.size();
            ++ans;
            for(auto it: comp)
            {
                if(adj[it].size() != sz-1) 
                {
                    ans--;
                    break;
                }
            }
            
        }
        return ans;
    }
