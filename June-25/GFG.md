## Problem of the Day - [<a href="https://leetcode.com/problems/snapshot-array/"> Unique rows in boolean matrix </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  vector< vector< int > > uniqueRow(int M[MAX][MAX],int row,int col){
        unordered_set< long long > set; 
        vector< vector< int > > res;
        
        for(int i=0; i < row; i++){
            long long sum = 0;
            vector<int> temp;
            for(int j=0; j < col; j++){
                temp.push_back(M[i][j]);
                if(M[i][j] == 1){
                    sum += pow(2,j);
                } 
            }
            if(set.find(sum) == set.end()){
                set.insert(sum);
                res.push_back(temp);
            }
        }
        return res;
    }
</pre>
