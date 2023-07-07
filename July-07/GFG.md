### Problem of the day - [ <a href="https://practice.geeksforgeeks.org/problems/merge-two-sorted-arrays-1587115620/1"> Merge Without Extra Space</a>]
#### Solution :
<pre>
  void swap(long long *x,long long *y){
            int temp = *x;
            *x = *y;
            *y = temp;
        }
        //Function to merge the arrays.
        void swapIfGreater(long long arr1[], long long arr2[],int i,int j){
            if(arr1[i]>arr2[j])
                swap(&arr1[i],&arr2[j]);
        }
        //Function to merge the arrays.
        void merge(long long arr1[], long long arr2[], int n, int m) 
        { 
            long long len = n+m;
            long long gap = len/2 + len%2;
            while(gap){
                long long low = 0;
                long long high = gap;
                while(high<n+m){
                    if(high<n){
                        if(arr1[low]>arr1[high]){
                            int temp = arr1[low];
                            arr1[low] = arr1[high];
                            arr1[high] = temp;
                        }
                        
                    }
                    else if(low>=n){
                        if(arr2[low-n]>arr2[high-n]){
                            int temp = arr2[low-n];
                            arr2[low-n] = arr2[high-n];
                            arr2[high-n] = temp;
                        }
                    }
                    else{
                        if(arr1[low]>arr2[high-n]){
                            int temp = arr1[low];
                            arr1[low] = arr2[high-n];
                            arr2[high-n] = temp;
                        }
                    }
                    low++;
                    high++;
                }
                if(gap==1)
                    break;
                gap = gap/2 + gap%2;
            }
        }
</pre>
