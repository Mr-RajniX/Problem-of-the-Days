#### Problem of the Day : [Transitive closure of a Graph](https://practice.geeksforgeeks.org/problems/transitive-closure-of-a-graph0930/1)

#### Solution :
<pre>
  vector< vector< int>> transitiveClosure(int N, vector< vector< int>> graph){
         for(int k=0;k < N;k++) {
            for(int i=0;i < N;i++) {
                for(int j=0;j < N;j++) {
                    if(i==j) graph[i][j] = 1;
                    if(graph[i][j]==0) {
                        if(graph[i][k]==1 && graph[k][j]==1) {
                            graph[i][j]=1;
                        }
                    }
                }
            }
        }
        return graph;
    }
</pre>
