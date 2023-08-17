### Problem of the day : [542. 01 Matrix](https://leetcode.com/problems/01-matrix/)

#### Solution :
<pre>
  vector < vector < int > > updateMatrix(vector < vector < int > >& A) {
        int n = A.size();
        int m = A[0].size();
        
        if (A[0][0] != 0) A[0][0] = m + n;
        
        for (int j = 1; j < m; j++) {
            if (A[0][j] != 0) A[0][j] = A[0][j - 1] + 1;
        }
        
        for (int i = 1; i < n; i++) {
            if (A[i][0] != 0) A[i][0] = A[i - 1][0] + 1;
        }
        
        for (int i = 1; i < n; i++) {
            for (int j = 1; j < m; j++) {
                if (A[i][j] != 0) A[i][j] = min(A[i - 1][j], A[i][j - 1]) + 1;
            }
        }
        
        for (int j = m - 2; j >= 0; j--) {
            if (A[n - 1][j] != 0) A[n - 1][j] = min(A[n - 1][j], A[n - 1][j + 1] + 1);
        }
        
        for (int i = n - 2; i >= 0; i--) {
            if (A[i][m - 1] != 0) A[i][m - 1] = min(A[i][m - 1], A[i + 1][m - 1] + 1);
        }
        
        for (int i = n - 2; i >= 0; i--) {
            for (int j = m - 2; j >= 0; j--) {
                if (A[i][j] != 0) A[i][j] = min(A[i][j], min(A[i + 1][j], A[i][j + 1]) + 1);
            }
        }
        
        return A;
    }
</pre>
