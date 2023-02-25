## Problem of the Day - [<a href="https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/"> 121. Best Time to Buy and Sell Stock </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int maxProfit(vector<int>& prices) {

        if (prices.size() == 1) return 0;

        int low = 0;
        int maxprofit = 0;

        for (int i = 0; i < prices.size(); ++i) {
            if (prices[i] < prices[low]) {
                low = i;
                continue;
            }
            maxprofit= max(maxprofit, prices[i] - prices[low]);
        }
        return maxprofit;
    }
</pre>
