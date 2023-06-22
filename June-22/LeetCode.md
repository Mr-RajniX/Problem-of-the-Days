## Problem of the Day - [<a href="https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-transaction-fee/"> 714. Best Time to Buy and Sell Stock with Transaction Fee </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int maxProfit(vector< int >& prices, int fee) {
        int buy = INT_MIN;
        int sell = 0;
        for(int s : prices){
            buy = max(buy,sell-s);
            sell = max(sell, buy + s - fee);
        }
        return sell;
    }
</pre>
