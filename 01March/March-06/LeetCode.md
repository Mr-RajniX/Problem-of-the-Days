## Problem of the Day - [<a href="https://leetcode.com/problems/kth-missing-positive-number/description/"> 1539. Kth Missing Positive Number </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int findKthPositive(vector<int>& arr, int k) {
        int n = arr.size();
        int start = 0, end = n-1;
        while (start <= end) {
            int mid = start + (end - start) / 2;
            if (arr[mid] - (mid + 1) < k)
                start = mid + 1;
            else
                end = mid - 1;
        }
        return start + k;
    }
</pre>
