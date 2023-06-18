## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/find-number-of-closed-islands/1"> Find number of closed islands </a>]


#### ⭐<ins>Solution Function Code #1</ins> -

     int closedIslands(vector<vector<int>>& grid, int n, int m) {
          vector<vector<bool>>vis(n,vector<bool>(m,false));
          int ans=0;
          for(int i=0;i<n;i++){
              for(int j=0;j<m;j++){
                  if(grid[i][j]==1 && vis[i][j]==false){
                      if(dfs(grid,n,m,i,j,vis)){
                          ans++;
                      }
                  }
              }
          }
          return ans;
      }
      bool dfs(vector<vector<int>>& grid,int n,int m,int i,int j,vector<vector<bool>>&vis){
          if(i<0 || i>=n || j<0 || j>=m){
              return false;
          }
          if(vis[i][j] || grid[i][j]==0){
              return true;
          }
          vis[i][j]=true;
          bool l=dfs(grid,n,m,i,j-1,vis);
          bool r=dfs(grid,n,m,i,j+1,vis);
          bool u=dfs(grid,n,m,i-1,j,vis);
          bool d=dfs(grid,n,m,i+1,j,vis);
          return l && r && u && d;

      }

