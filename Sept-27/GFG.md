### Problem of the Day : [Find the closest pair from two arrays](https://practice.geeksforgeeks.org/problems/find-the-closest-pair-from-two-arrays4215/1)

##### Solution :
<pre>
  vector< int> printClosest(int arr[], int brr[], int n, int m, int x) {
        int it1=0,it2=m-1;
        int h=0,j=0;
        int mn=INT_MAX;
        vector< int> ans(2);
        while(it1 < n && it2 >= 0){
            int sum = arr[it1] + brr[it2];
            int dp = abs(sum-x);
            if(mn > dp){
                mn=dp;
                ans[0]=arr[it1];
                ans[1]=brr[it2];
            }
            if(sum >= x)
                it2--;
            else
                it1++;
        }
       return ans;
    }
</pre>
