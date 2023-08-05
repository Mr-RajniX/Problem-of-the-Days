### Problem of the Day : [Chocolate Distribution Problem](https://practice.geeksforgeeks.org/problems/chocolate-distribution-problem3825/1)

#### Solution :
<pre>
  long long findMinDiff(vector< long long > a, long long n, long long m){
        sort(a.begin(),a.end());
        long long ans = INT_MAX;
        for(int i=0;i <= n-m;i++){
            ans = min(ans,a[m-1+i]-a[i]);
        }
        return ans;
    }   
</pre>
