### Problem of the Day : [Find triplets with zero sum](https://practice.geeksforgeeks.org/problems/find-triplets-with-zero-sum/1)

#### Solution :
<pre>
  bool findTriplets(int arr[], int n){  
        sort(arr,arr+n);
        for(int i=0; i < n ; i++){
            int left = i+1;
            int right = n-1;
            while(left < right){
                if(arr[i] + arr[left] + arr[right] == 0) return true;
                else if(arr[i] + arr[left] + arr[right] > 0) right--;
                else left++;
            }
        }return false;
    }
</pre>
