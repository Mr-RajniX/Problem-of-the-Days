## Problem of the Day - [<a href="https://leetcode.com/problems/reorder-routes-to-make-all-paths-lead-to-the-city-zero/description/"> 1466. Reorder Routes to Make All Paths Lead to the City Zero </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int minReorder(int n, vector<vector<int>>& connections) {
        vector<vector<pair<int,int>>> graph(n);
        for(auto &v: connections){
            graph[v[0]].push_back({v[1],1});
            graph[v[1]].push_back({v[0],0});
        }
        queue<pair<int,int>> q;
        q.push({0,0});
        vector<bool> vis(n,false);
        int ans=0;
        while(!q.empty()){
            auto p=q.front();
            q.pop();
            vis[p.first]=true;
            ans+=p.second;
            for(auto &x: graph[p.first]){
                if(vis[x.first])continue;
                q.push(x);
            }
        }
        return ans;
    }
</pre>
