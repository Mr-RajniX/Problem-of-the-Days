### Problem of the Day : [DFS of Graph](https://practice.geeksforgeeks.org/problems/depth-first-traversal-for-a-graph/1)

#### Solution :
<pre>
  vector< int >ans;
    void solve(vector<int>adj[],vector< int >&vis,int start){
        for(auto it:adj[start]){
            if(vis[it]==0){
                vis[it]=1;
                ans.push_back(it);
                solve(adj,vis,it);
            }
        }
    }
    vector<int> dfsOfGraph(int V, vector< int > adj[]) {
        // Code here
        vector< int >vis(V,0);
        ans.push_back(0);
        vis[0]=1;
        solve(adj,vis,0);
        return ans;
    }
</pre>
