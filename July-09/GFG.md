### Problem of the Day : [Smallest Positive missing number](https://practice.geeksforgeeks.org/problems/smallest-positive-missing-number-1587115621/1)

#### Solution :
<pre>
  int missingNumber(int arr[], int n) { 
        int i =0 ;
        while(i< n){
            if(arr[i] > 0 && arr[i] < n  && arr[i] != arr[arr[i]-1])
                swap(arr[i], arr[arr[i] - 1]);
            else i++;
        }
        for(int i=0; i< n; i++){
            if(arr[i] != i+1) return i+1;
        }return n+1;
    } 
</pre>
