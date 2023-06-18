## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/d54c71dc974b7db3a200eb63f34e3d1cba955d86/1"> Maximum Triplet product </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    long long maxTripletProduct(long long arr[], int n){
    	sort(arr,arr+n);
    	long long mn1=arr[0],mn2=arr[1],mx1=arr[n-1],mx2=arr[n-2],mx3=arr[n-3];
    	return max((mn1*mn2*mx1),(mx1*mx2*mx3));
    }
</pre>
