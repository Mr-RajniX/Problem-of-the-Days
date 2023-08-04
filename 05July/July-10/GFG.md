### Problem of the Day : [Transpose of Matrix] (https://practice.geeksforgeeks.org/problems/transpose-of-matrix-1587115621/1)

#### Solution :
<pre>
  void transpose(vector< vector< int > >& matrix, int n){ 
        for(int i=0; i < n; i++){
            for(int j=i; j < n; j++){
                if(i!=j) swap(matrix[i][j], matrix[j][i]);
            }
        }
    }
</pre>
