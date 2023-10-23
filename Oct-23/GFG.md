#### Problem of the Day : [Maximum sum increasing subsequence](https://practice.geeksforgeeks.org/problems/maximum-sum-increasing-subsequence4749/1)

#### Solution :
<pre>
  int maxSumIS(int arr[], int n) {  
	    int ans = 0;
	    vector< int> v;
	    for(int i=0; i < n; i++) v.push_back(arr[i]);
	    for(int i = 1; i < n; i++)
	        for(int j = 0; j < i; j++)
	            if( arr[i] > arr[j] && v[i] < v[j] + arr[i])
	                v[i] = v[j] + arr[i];
	    for(int i = 0; i < n; i++)
	        if(ans < v[i]) ans = v[i];
	    return ans;
	}  
</pre>
