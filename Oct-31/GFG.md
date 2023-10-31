#### Problem of the Day : [Move all zeroes to end of array](https://practice.geeksforgeeks.org/problems/move-all-zeroes-to-end-of-array0751/1)

#### Solution :
<pre>
  void pushZerosToEnd(int arr[], int n) {
	    int s = 0, i = 0;
	    while( s < n){
	        if(arr[s] != 0){
	            swap(arr[s] , arr[i++]);
	        }s++;
	    }
	}
</pre>
