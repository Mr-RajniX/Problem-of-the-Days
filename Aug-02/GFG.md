### Problem of the Day : [Shortest Source to Destination Path](https://practice.geeksforgeeks.org/problems/shortest-source-to-destination-path3544/1)

#### Solution : 
<pre>
  bool isValid(int i,int j,vector< vector< int > &visited,vector< vector< int > > & A,int N,int M){
        if(i < 0 || i  >= N || j < 0 || j >= M || visited[i][j]==1 || A[i][j]==0){
          return false;
        }
        return true;
    }
  
    int shortestDistance(int N, int M, vector< vector< int > > A, int X, int Y) {
        // code here
        if(X==0 && Y==0) return 0;
        if(A[0][0]==0)
        {
            return -1;
        }
        queue< pair< pair< int, int >, int > > q;
        q.push({{0, 0}, 0});
        vector< vector< int > > visit(N, vector< int >(M, 0));
        int dr[]={-1, 0, 1, 0};
        int dc[]={0, 1, 0, -1};
        while(!q.empty()){
            auto it=q.front();
            q.pop();
            int r=it.first.first;
            int c=it.first.second;
            int dist=it.second;
            
            for(int i=0; i<4; i++){
                int nr=r+dr[i];
                int nc=c+dc[i];
                
                if(isValid(nr, nc, visit, A, N, M)){
                    if(nr==X && nc==Y){
                    return dist+1;
                    }
                    visit[nr][nc]=1;
                    q.push({{nr, nc}, dist+1});
                }
            }
        }
        return -1;
    }
</pre>
