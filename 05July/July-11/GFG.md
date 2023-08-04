### Problem of the Day : [Find kth element of spiral matrix](https://practice.geeksforgeeks.org/problems/find-nth-element-of-spiral-matrix/1)

#### Solution :
<pre>
  int findK(int a[MAX][MAX],int n,int m,int k)
    {
 		int i=0,l=n,r=m;
 		while(k>(2*(l+r)-4)){
 		    i++;
 		    k-=(2*(l+r)-4);
 		    l-=2;r-=2;
 		}
 		if(k<=(m-2*i)) return a[i][i+k-1];
 		k-=(m-2*i);
 		if(k<=(n-2*i-1)) return a[i+k][m-i-1];
 		k-=(n-2*i-1);
 		if(k<=(m-2*i-1)) return a[n-i-1][m-i-k-1];
 		k-=(m-2*i-1);
 		return a[n-i-k-1][i];
    }
</pre>
