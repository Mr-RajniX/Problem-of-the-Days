### Problem of the Day : [Number of occurrence](Number of occurrence)

#### solution :
<pre>
  int count(int arr[], int n, int x) {
	    int a=upper_bound(arr,arr+n,x)-arr;
        int b=lower_bound(arr,arr+n,x)-arr;
        return (a-b);
	}
</pre>
