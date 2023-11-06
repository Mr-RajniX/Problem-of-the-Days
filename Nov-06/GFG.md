#### Problem of the Day : [Letters Collection](https://www.geeksforgeeks.org/problems/c-letters-collection4552/1)

#### Solution :
<pre>
  vector< int> matrixSum(int n, int m, vector< vector< int>> mat, int q, vector< int> queries[]){
        vector< int> ans;
       
        for(int i=0; i < q;i++){
           
            int sum= 0;
            int x = queries[i][1];
            int y = queries[i][2];
            int dis = queries[i][0];
           
            for(int j =-dis;j <= dis;j++){
               for(int k=-dis;k <= dis;k++){
                    
                    if(dis==2){
                       if((j==1||j==-1||j==0)&&(k==-1||k==1||k==0)) continue;
                    }
                     
                    if(x+j >= 0 && x+j < n && y+k >= 0 && y+k < m){
                        sum += mat[x+j][y+k];
                    }
                }
            }
            if(dis==1)
                sum -= mat[x][y];
            ans.push_back(sum);
        }
        return ans;
    }
</pre>
