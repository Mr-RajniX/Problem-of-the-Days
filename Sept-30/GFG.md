### Problem of the Day : [Boolean Matrix](https://practice.geeksforgeeks.org/problems/boolean-matrix-problem-1587115620/1)

##### Solution :
<pre>
  void booleanMatrix(vector< vector< int> > &matrix){
        int n=matrix.size();
        int m=matrix[0].size();
        unordered_map< int,bool> row,col;
        for(int i=0;i < n;i++){
            for(int j=0;j < m;j++){
                if(matrix[i][j]){
                    row[i]=true;
                    col[j]=true;
                }
            }
        }
        for(int i=0;i < n;i++){
            for(int j=0;j < m;j++){
                if(row[i] or col[j])
                    matrix[i][j]=1;
            }
        }
    }
</pre>
