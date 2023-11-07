#### Problem of the Day : [Sum of upper and lower triangles](https://www.geeksforgeeks.org/problems/sum-of-upper-and-lower-triangles-1587115621/1)

#### Solution :
<pre>
  vector< int> sumTriangles(const vector< vector< int> >& matrix, int n){
        int upper = 0, lower = 0;
        for(int i = 0; i < n; i++){
            for(int j = 0; j < n; j++){
                if(i <= j)  upper += matrix[i][j];
                if(i >= j)  lower += matrix[i][j];
            }
        }
        return {upper, lower};
    }
</pre>
