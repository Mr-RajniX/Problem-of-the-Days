### Problem of the day : [Find duplicates in an array](https://practice.geeksforgeeks.org/problems/find-duplicates-in-an-array/1)

#### Solution :
<pre>
  vector< int> duplicates(int arr[], int n) {
        vector< int> ans;
        sort(arr,arr+n);
        int check =-1;
        for(int i = 1 ; i < n ; i++ ){
            if(arr[i] == check) continue;
            if(arr[i] == arr[i-1]){
                check = arr[i];
                ans.push_back(check);
            }
        }
        if(ans.empty()) ans.push_back(-1);
        return ans;
    }
</pre>
