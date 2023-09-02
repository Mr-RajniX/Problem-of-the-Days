### Problem of the Day : [Solve the Sudoku](https://practice.geeksforgeeks.org/problems/solve-the-sudoku-1587115621/1)

#### Solution :
<pre>
  bool isvalid(int row,int col,int val,int grid[9][9]){
        for(int i=0;i < 9;i++){
            if(grid[row][i]==val)return false;
            if(grid[i][col]==val)return false;
            if(grid[3*(row/3)+(i/3)][3*(col/3)+(i%3)]==val)return false;
        }
        return true;
    }
    bool SolveSudoku(int grid[N][N])  { 
         for(int i=0;i < N;i++){
            for(int j=0;j < N;j++){
                if(grid[i][j]==0){
                    for(int k=1;k <= 9;k++){
                        if(isvalid(i,j,k,grid)){
                            grid[i][j]=k;
                            if(SolveSudoku(grid))return true;
                            else grid[i][j]=0;
                        }
                    }
                    return false;
                }
            }
        }
        return true;
    }
    
    //Function to print grids of the Sudoku.
    void printGrid (int grid[N][N]) {
        for(int i=0;i < N;i++)
            for(int j=0;j < N;j++)
                cout << grid[i][j]<<" ";
    }
</pre>
