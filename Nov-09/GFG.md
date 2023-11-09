#### Problem of the Day : [Predict the Column](https://www.geeksforgeeks.org/problems/predict-the-column/1)

#### Solution :
<pre>
  int columnWithMaxZeros(vector< vector< int>>arr,int N){
        int mx = -1;
        int maxIdx = -1;
        for(int col=N-1; col>=0; col--) {
            int zeros=0;
            for(int row=0; row < N; row++) {
                if(arr[row][col]==0){
                    zeros++;
                    mx = max(mx, zeros);
                }
            }
            if(mx!=-1 && zeros>=mx){
                maxIdx=col;
            }
        }
        return maxIdx;
    }
</pre>
