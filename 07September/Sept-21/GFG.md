### Problem of the Day : [Stickler Thief](https://practice.geeksforgeeks.org/problems/stickler-theif-1587115621/1)

#### Solution :
<pre>
  int FindMaxSum(int arr[], int n){
        if(n==1) return arr[0];
        if(n==2) return max(arr[0], arr[1]);
        
        arr[1] = max(arr[0], arr[1]);
        for(int i = 2; i < n; i++){
            int visit = arr[i] + arr[i-2];
            arr[i] = max(visit, arr[i-1]);
        }return arr[n-1];
    }
</pre>
