## Problem of the Day - [<a href="https://leetcode.com/problems/matrix-diagonal-sum/"> 1572. Matrix Diagonal Sum </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     int diagonalSum(vector<vector<int>>& mat) {
          int n = mat.size() , ans =0;
          for(int i=0;i<n;i++){
              ans+=mat[i][i];
              if( i != n-i-1) ans+=mat[i][n-i-1];
          }
          return ans;
      }

