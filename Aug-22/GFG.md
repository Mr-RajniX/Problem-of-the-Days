### Problem of the Day : [Make Matrix Beautiful](https://practice.geeksforgeeks.org/problems/make-matrix-beautiful-1587115620/1)

#### Solution : 
<pre>
  int findMinOpeartion(vector< vector< int> > matrix, int n){
        int maxi = INT_MIN, ans = 0;
        for( int i=0; i < n; i++){
            int row_sum = 0 , col_sum = 0;
            for( int j =0 ; j < n; j++){
                row_sum += matrix[i][j];
                col_sum += matrix[j][i];
            }
            maxi = max(maxi , max(row_sum, col_sum));  
        }
        for(int i=0 ; i < n; i++){
            int sum = 0;
            for(int j = 0; j < n; j++) sum += matrix[i][j];
            ans += maxi - sum;
        }return ans;
    } 
</pre>
