#### Problem of the Day : [Making A Large Island](https://practice.geeksforgeeks.org/problems/making-a-large-island/1)

#### Solution :
<pre>
    int n, m;
    int di[4] = {-1, 0, 1, 0};
    int dj[4] = {0, -1, 0, 1};
    // main function
    int largestIsland(vector< vector< int>>& grid) {
        n = grid.size();
        m = grid[0].size();
        int mx = 0, key = 1;
        vector< vector< int>> vis(n+1, vector< int>(m+1, 0));
        map< int, int> mp;
        for(int i = 0; i < n; i++){
            for(int j = 0; j < m; j++){
                if(!vis[i][j] && grid[i][j]){
                    key++;
                    int sz = dfs(i, j, grid, vis, key);
                    mp[key] = sz;
                    mx = max(mx, sz);
                }
            }
        }
        for(int i = 0 ; i < n; i++){
            for(int j = 0; j < m; j++){
                if(grid[i][j] == 0){
                    int newSize = 1;
                    set< int> st;
                    for(int k = 0; k < 4; k++){
                        int ni = i + di[k];
                        int nj = j + dj[k];
                        if(isValid(ni, nj) && grid[ni][nj])
                            st.insert(vis[ni][nj]);
                    }
                    for(auto it : st)
                        newSize += mp[it];
                    mx = max(mx, newSize);
                }
            }
        }return mx;
    }
    bool isValid(int ni, int nj){
        if(ni >= 0 && nj >= 0 && ni < n && nj < m)
            return true;
        return false;
    }
    
    int dfs(int i, int j, vector< vector< int>>&grid, vector< vector< int>>&vis, int &key){
        vis[i][j] = key;
        int sz = 1;
        for(int k = 0; k < 4; k++){
            int ni = i + di[k];
            int nj = j + dj[k];
            if(isValid(ni, nj) && !vis[ni][nj] && grid[ni][nj])
                sz += dfs(ni, nj, grid, vis, key);
        } return sz;
    }
</pre>
