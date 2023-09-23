### Problem of the Day : [Equilibrium Point](https://practice.geeksforgeeks.org/problems/equilibrium-point-1587115620/1)

#### Solution :
<pre>
  int equilibriumPoint(long long a[], int n) {
        long long sum=0,s=0,i=0,j=n-1;
        while (i < j){
          if (sum < s) sum=sum+a[i++];
          else s=s+a[j--];
        }
        if (sum==s) return i+1;
       return -1;
    }
</pre>
