## Problem of the Day - [<a href="https://leetcode.com/problems/as-far-from-land-as-possible/description/"> 1162. As Far from Land as Possible </a>]


#### ⭐<ins>Solution Function Code</ins> -

        int maxDistance(vector<vector<int>>& grid) {
        int n = grid.size();
        int dist=0, size;
        queue<pair<int, int>> q;
        int drow[] = {0, -1, 0, 1}, dcol[] = {-1, 0, 1, 0};
        for(int i=0;i<n;i++)
            for(int j=0;j<n;j++)    
                if(grid[i][j] == 1)
                    q.push({i, j});
        if(q.size() == n*n)
            return -1;
        while(!q.empty()){
            size = q.size();
            dist++;
            while(size--){
                int r = q.front().first, c = q.front().second;
                q.pop();
                for(int i=0;i<4;i++){
                    int nrow = r + drow[i], ncol = c + dcol[i];
                    if(nrow>=0 && ncol>=0 && nrow<n && ncol<n && grid[nrow][ncol]==0){
                        grid[nrow][ncol] = 1;
                        q.push({nrow, ncol});
                    } 
                }
            }
        }
        return dist-1;
    }


