### Problem of the Day : [Number Of Enclaves](https://practice.geeksforgeeks.org/problems/number-of-enclaves/1)

##### Solution :
<pre>
  int numberOfEnclaves(vector< vector< int>> &grid) {
        int n = grid.size();
        int m = grid[0].size();
        vector< vector< int>> directions = {{1, 0}, {0, 1}, {-1, 0}, {0, -1}};
        for(int i = 0; i < n; i++){
            for(int j = 0; j < m; j++){
                if(grid[i][j] == 1 && (i == 0 || i == n-1 || j == 0 ||j == m-1))
                    dfs(grid, directions, i, j, n, m);
            }
        }
        int cnt = 0;
        for(int i = 0; i < n; i++){
            for(int j = 0; j < m; j++){
                if(grid[i][j] == 1)
                    cnt++;
            }
        }
        return cnt;
    }
    void dfs(vector< vector< int >> &grid, vector< vector< int>> &directions, int i, int j, int n, int m){
        grid[i][j] = -1;
        for(auto &dir : directions){
            int i_ = i + dir[0];
            int j_ = j + dir[1];
            
            if(i_ >= 0 && i_ < n && j_ >= 0 && j_ < m && grid[i_][j_] == 1)
                dfs(grid, directions, i_, j_, n , m);
        }
    }
</pre>
