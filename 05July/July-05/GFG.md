### Problem of the Day - [ <a href="https://practice.geeksforgeeks.org/problems/stock-buy-and-sell2615/1"> Stock buy and sell II </a>]

#### Solution #1 :
<pre>
  int stockBuyAndSell(int n, vector< int > &prices) {
        int ans = 0;
        for(int i=0; i < n-1; i++){
            ans = max(ans, ans+prices[i+1]-prices[i]);
        }return ans;
    }
</pre>
