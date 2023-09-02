### Problem of the Day : [Shortest path in Directed Acyclic Graph](https://practice.geeksforgeeks.org/problems/shortest-path-in-undirected-graph/1)

#### Solution :
<pre>
  vector< int > shortestPath(int N,int M, vector< vector< int > >& edges){
        vector < int > distance (N , 1e8);
        distance[0] = 0;
        
        for( int i=0; i < M; i++){
            int r = edges[i][0];
            int c = edges[i][1];
            int cost = edges[i][2];
            if(distance[c] > cost + distance[r] ) distance[c] = cost + distance[r];
        }
        for(int i = 0 ; i < distance.size(); i++)
            if(distance[i] == 1e8) distance[i] = -1;
        return distance;
    }
</pre>
