#### Problem of the Day : [Find Transition Point](https://www.geeksforgeeks.org/problems/find-transition-point-1587115620/1)

#### Solution :
<pre>
  int transitionPoint(int arr[], int n) {
        int low = 0;
        int high = n-1;
        while(low < high) {
            int mid = (low + high) >> 1;
            if(arr[mid] == 1)
                high = mid;
            else 
                low = mid+1;
        }
        if(arr[low] == 0)
            return -1;
        return low;
    }
</pre>
