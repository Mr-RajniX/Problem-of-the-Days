## Problem of the Day - [<a href="https://leetcode.com/problems/number-of-closed-islands/description/"> 1254. Number of Closed Islands </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    int closedIsland(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        int count = 0;
        vector<vector<bool>> visited(m, vector<bool>(n, false));
        for (int i = 1; i < m - 1; i++) {
            for (int j = 1; j < n - 1; j++) {
                if (grid[i][j] == 0 && !visited[i][j]) {
                    bool isClosed = dfs(grid, visited, i, j);
                    if (isClosed) {
                        count++;
                    }
                }
            }
        }
        return count;
    }
    
    bool dfs(vector<vector<int>>& grid, vector<vector<bool>>& visited, int i, int j) {
        int m = grid.size();
        int n = grid[0].size();
        if (i < 0 || i >= m || j < 0 || j >= n) {
            return false;
        }
        if (visited[i][j]) {
            return true;
        }
        visited[i][j] = true;
        if (grid[i][j] == 1) {
            return true;
        }
        bool isClosed = true;
        isClosed &= dfs(grid, visited, i - 1, j);
        isClosed &= dfs(grid, visited, i + 1, j);
        isClosed &= dfs(grid, visited, i, j - 1);
        isClosed &= dfs(grid, visited, i, j + 1);
        return isClosed;
    }
</pre>
