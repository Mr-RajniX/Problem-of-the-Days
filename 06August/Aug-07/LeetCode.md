### Problem of the Day : [74. Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/)

#### Solution :
<pre>
  bool searchMatrix(vector< vector< int > >& matrix, int target) {
        int col = matrix.size();
        int row = matrix[0].size();
        int start = 0, end = col*row - 1;

        while(start <= end){
            int mid = start + ( end - start ) / 2;
            int midVal = matrix[mid / row] [mid % row];
            if (midVal == target) return true;
            else if( midVal < target ) start = mid + 1;
            else end = mid -1 ;
        }return false;
    }
</pre>
