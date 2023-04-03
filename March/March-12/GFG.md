## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/77e1c3e12cd148f835d53eb168d4472b2ff539fa/1"> Binary matrix having maximum number of 1s </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    vector<int> findMaxRow(vector<vector<int>> mat, int N) {
        int mxcount = 0;
        int row_num = 0;
        for(int i = 0; i<N; i++){
             vector<int>::iterator upper;
             upper = upper_bound(mat[i].begin(), mat[i].end(), 0) ;
             int temp =  N - (upper - mat[i].begin());
             if(temp > mxcount){
                 mxcount = temp;
                 row_num = i;
             }
        }
       return {row_num , mxcount};
    }
</pre>
