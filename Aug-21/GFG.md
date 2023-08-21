### Problem of the Day : [Surround the 1's](https://practice.geeksforgeeks.org/problems/surround-the-1s2505/1)

#### Solution :
<pre>
  int Count(vector< vector< int > >& matrix) {
        int height = matrix.size();
        int width = matrix[0].size();
        int count_0;
        int ans{};
        for(int i{}; i < height; i++){
            for(int j{}; j < width; j++){
                if(matrix[i][j] == 0)
                    continue;
                    
                count_0 = 0;
                if(j - 1 >= 0)
                    if(matrix[i][j-1] == 0)
                        count_0++;
                if(j + 1 < width)
                    if(matrix[i][j+1] == 0)
                        count_0++;  
                if(i - 1 >= 0){
                    if(matrix[i-1][j] == 0)
                        count_0++;
                    if(j - 1 >= 0)
                        if(matrix[i-1][j-1] == 0)
                            count_0++;
                    if(j + 1 < width)
                        if(matrix[i-1][j+1] == 0)
                            count_0++; 
                }
                if(i + 1 < height){
                    if(matrix[i+1][j] == 0)
                        count_0++;
                    if(j - 1 >= 0)
                        if(matrix[i+1][j-1] == 0)
                            count_0++;
                    if(j + 1 < width)
                        if(matrix[i+1][j+1] == 0)
                            count_0++; 
                }
                if(count_0 > 0 && count_0 % 2 == 0)
                    ans++;
            }
        }
        return ans;
    }
</pre>
