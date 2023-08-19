### Problem of the day : [Subarray with given sum](https://practice.geeksforgeeks.org/problems/subarray-with-given-sum-1587115621/1)

#### Solution :
<pre>
  vector < int > subarraySum(vector < int > arr, int n, long long s){
        int st = 0, mid = 0;
        int sum = 0;
        while(mid < n){
            sum += arr[mid];
            while(st < mid && sum > s){
                sum -= arr[st];
                st++;
            }
            if( sum == s) return {st+1, mid+1};
            mid++;
        }return {-1};
    }
</pre>
