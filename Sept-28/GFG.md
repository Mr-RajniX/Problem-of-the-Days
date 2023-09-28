### Problem of the Day : [Wave Array](https://practice.geeksforgeeks.org/problems/wave-array-1587115621/1)

##### Solution :
<pre>
  void convertToWave(int n, vector< int>& arr){
        int i = 0,j=1;
        while(j < n){
            swap(arr[i],arr[j]);
            i = i+2;
            j = j+2;
        }
    }
</pre>
