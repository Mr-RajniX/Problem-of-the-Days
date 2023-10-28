#### Problem of the Day : [Bleak Numbers](https://practice.geeksforgeeks.org/problems/bleak-numbers1552/1)

#### Solution :
<pre>
  int is_bleak(int n){
	    for(int i=0;i<=log2(n);i++)if(__builtin_popcount(n-i) == i) return false; 
            return true;
	}
</pre>
