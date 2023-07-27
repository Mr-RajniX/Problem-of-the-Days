### Problem of the Day : [Heap Sort](https://practice.geeksforgeeks.org/problems/heap-sort/1)

#### Solution : 
<pre>
  public:
    //Heapify function to maintain heap property.
    void heapify(int arr[], int n, int i)  {
        int node=i;
        int left=2*i+1;
        int right=2*i+2;
        if(left < n && right < n){
            if(arr[left] < arr[right]){
                node=right;
            }
            else{
                node=left;
            }
        }
        else if(left < n){
            node=left;
        }
        else if(right < n){
            node=right;
        }
        if(node!=i && arr[i] < arr[node]){
            int t=arr[i];
            arr[i]=arr[node];
            arr[node]=t;
            heapify(arr,n,node);
        }
    }

    public:
    //Function to build a Heap from array.
    void buildHeap(int arr[], int n)  {
        for(int i= n/2-1; i >= 0; i--)  heapify(arr,n,i);
    }

    
    public:
    //Function to sort an array using Heap Sort.
    void heapSort(int arr[], int n){
        buildHeap(arr,n);
        while(n--){
            swap(arr[0],arr[n]);
            heapify(arr, n , 0);
        }
    }
</pre>
