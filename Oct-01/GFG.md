### Problem of the Day : [Boundary traversal of matrix](https://practice.geeksforgeeks.org/problems/boundary-traversal-of-matrix-1587115620/1)

##### Solution :
<pre>
  vector< int> boundaryTraversal(vector< vector< int> > matrix, int n, int m) {
        vector< int> ans;
        for(int i = 0; i < m; i++)
            ans.push_back(matrix[0][i]);
        for(int i = 1; i < n - 1; i++)
            ans.push_back(matrix[i][m - 1]);
        if(n == 1)
            return ans;
        for(int i = m - 1; i >= 0; i--)
            ans.push_back(matrix[n - 1][i]);
        if(m == 1)
            return ans;
        for(int i = n - 2; i >= 1; i--)
            ans.push_back(matrix[i][0]);
        return ans;
    }
</pre>
