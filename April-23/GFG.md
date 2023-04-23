## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/7d62c8606123a199720c9b6885249dc9ac651bb7/1"> Minimum Number </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int minimumNumber(int n,vector<int> &arr){
        int mini = INT_MAX;
        for(int i = 0; i < arr.size(); i++){
            if(arr[i]%2 != 0) return 1;
            
            mini = min(mini, arr[i]);
        }
        return mini;
    }
</pre>
