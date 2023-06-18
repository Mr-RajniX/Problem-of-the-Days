## Problem of the Day - [<a href="https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/description/"> 1011. Capacity To Ship Packages Within D Days </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int shipWithinDays(vector<int>& weights, int days) {
        int lo = *max_element(weights.begin(), weights.end());
        int hi = accumulate(weights.begin(), weights.end(), 0);
        while (lo < hi) {
            int mid = lo + (hi - lo) / 2;
            int cur = 0, need = 1;
            for (int w : weights) {
                if (cur + w > mid) {
                    cur = 0;
                    need++;
                }
                cur += w;
            }
            if (need <= days) {
                hi = mid;
            } else {
                lo = mid + 1;
            }
        }
        return lo;
    }
</pre>
