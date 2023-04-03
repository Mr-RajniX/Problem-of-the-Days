## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/96161dfced02d544fc70c71d09b7a616fe726085/1"> Unique Paths in a Grid </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int MOD=1e9+7;
    int helper(vector<vector<int>>& grid, int i, int j, int n, int m){
        if(i>=n || j>=m || grid[i][j]==0)return 0;
        if(i==n-1 && j==m-1)return 1;
        
        if(grid[i][j]<=0)return abs(grid[i][j]);
        
        grid[i][j] = -(helper(grid,i+1,j,n,m) + helper(grid,i,j+1,n,m))%MOD;
        return abs(grid[i][j]);
    }
    int uniquePaths(int n, int m, vector<vector<int>> &grid) {
        return helper(grid,0,0,n,m);
    }
</pre>
