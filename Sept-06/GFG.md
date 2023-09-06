### Problem of the Day : [Mother Vertex](https://practice.geeksforgeeks.org/problems/mother-vertex/1)

#### Solution : 
<pre>
  int findMotherVertex(int V, vector< int> adj[]){
	    vector< bool> visted(V, false);
        int ans=-1;
        for(int i=0; i < V; i++){
            if(!visted[i]){
                dfs(adj, i, visted);
                ans=i;
            }
        }
        fill(visted.begin(), visted.end(), false);
        dfs(adj, ans, visted);
     
        for (bool v : visted) 
            if (!v) 
                return -1;
        return ans;
	}
	
	void dfs(vector< int> adj[], int i, vector< bool> &visted ){
        visted[i]=true;
        for(auto x: adj[i]){
            if(visted[x])
            continue;
            dfs(adj, x,visted);
        }
    }
</pre>
