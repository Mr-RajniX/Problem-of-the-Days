#### Problem of the Day : [Level of Nodes](https://practice.geeksforgeeks.org/problems/level-of-nodes-1587115620/1)

#### Solution :
<pre>
  int nodeLevel(int V, vector< int> adj[], int X) {
	    queue< pair< int,int>>q;
	    vector< int>vis(V,0);
	    vis[0] = 1;
	    q.push({0,0});
	    while(!q.empty()){
	        int level = q.front().first;
	        int node = q.front().second;
	        q.pop();
	        if(node==X) return level;
	        for(auto it:adj[node]){
	            if(!vis[it]){
	                vis[it] = 1;
	                q.push({level+1,it});
	            }
	        }
	    }
	    return -1;
	}
</pre>
