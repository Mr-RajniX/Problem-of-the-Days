## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/7a33c749a79327b2889d420dd80342fff33aac6d/1"> Max Sum without Adjacents </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int maxi (int n1, int n2){
	    if(n1>=n2){
	        return n1;
	    }
	    return n2;
	}
	int findMaxSum(int *arr, int n) {
	    // code here
	    if(n==1) return arr[0]; 
	    if(n>2)  arr[n-3]+=arr[n-1];  
        for(int i=n-4;i>=0;i--){
            arr[i]+=maxi(arr[i+2],arr[i+3]); 
        }
        return maxi(arr[0],arr[1]);  
	}
</pre>
