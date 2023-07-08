## Problem of the day : [ <a href="https://practice.geeksforgeeks.org/problems/quick-sort/1">Quick Sort</a> ]

### Solution #1 :
<pre>
    void quickSort(int arr[], int low, int high){
        if(low < high){
            int p=partition(arr,low,high);
            quickSort(arr,low,p-1);
            quickSort(arr,p+1,high);
        }
    }
    int partition (int arr[], int low, int high){
        int pi=arr[low],i=low,j=high;
            while(i < j){
               while(arr[i] <= pi &&i <= high-1) i++;
               while(arr[j] > pi && j >= low+1) j--;
               if(i < j) swap(arr[i],arr[j]);
           }
           swap(arr[j],arr[low]);
           return j;
    }
</pre>
