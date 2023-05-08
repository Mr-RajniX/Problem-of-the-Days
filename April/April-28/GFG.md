## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/5a1277ffc1ec1d3a63d1a5d6b3920dd3d1294261/1"> Geek's Village and Wellss </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     vector<vector<int>> chefAndWells(int n,int m,vector<vector<char>> &c)
      {
          vector<vector<int>>res(n,vector<int>(m,0));

          vector<vector<int>>vis(n,vector<int>(m,0));

          queue<pair<pair<int,int>,int>>q;

          for(int i=0;i<n;i++)
          {
              for(int j=0;j<m;j++)
              {
                  if(c[i][j] == 'W'){
                      vis[i][j] = 1;
                      q.push({{i,j},0});
                      res[i][j] = 0;
                  }
              }
          }

          int delrow[] = {-1,0,1,0};
          int delcol[] = {0,1,0,-1};


          while(!q.empty())
          {
              auto it = q.front();
              int row = it.first.first;
              int col = it.first.second;
              int dis = it.second;
              q.pop();

              for(int i=0;i<4;i++)
              {
                  int nrow = row+delrow[i];
                  int ncol = col+delcol[i];

                  if(nrow>=0 and nrow<n and ncol>=0 and ncol<m and !vis[nrow][ncol] and (c[nrow][ncol] == 'H' || c[nrow][ncol] == '.') and res[nrow][ncol]==0)
                  {
                      vis[nrow][ncol] = 1;
                      res[nrow][ncol] = dis+2;
                      q.push({{nrow,ncol},2+dis});
                  }
              }
          }

          for(int i=0;i<n;i++)
          {
              for(int j=0;j<m;j++)
              {
                  if(!vis[i][j] and c[i][j] == 'H')
                      res[i][j] = -1;
                  if(c[i][j] == '.')
                      res[i][j] = 0;
              }
          }
          return res;
      }
