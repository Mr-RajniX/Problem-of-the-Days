#### Problem of the Day : [Pythagorean Triplet](https://www.geeksforgeeks.org/problems/pythagorean-triplet3018/1)

#### Solution :
<pre>
  bool checkTriplet(int arr[], int n) {
	    int a[n];
	    for(int i=0;i < n;i++)
	        a[i]=pow(arr[i],2);
	    unordered_map< int,bool>mp;
	    for(int i=0;i < n;i++)
	    mp[a[i]]=true;
	    
	    for(int i=0;i < n;i++)
	    {
	        for(int j=0;j < n;j++)
	        {
	            int sum=a[i]+a[j];
	            if(mp[sum]==true)
	            return true;
	        }
	    }
	    return false;
	}
</pre>
