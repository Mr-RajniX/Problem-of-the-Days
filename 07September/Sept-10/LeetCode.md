### Problem of the day : [1359. Count All Valid Pickup and Delivery Options](https://leetcode.com/problems/count-all-valid-pickup-and-delivery-options/)

#### Solution :
<pre>
  int countOrders(int n) {
        int mod = 1e9 + 7;
        if(n==1) return 1;
        long long ans = 1;
        for(int i = 1 ; i <= n; i++){
            ans *= (2 * i - 1) * i % mod;
        }
        return ans;
    }
</pre>
