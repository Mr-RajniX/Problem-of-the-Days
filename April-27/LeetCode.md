## Problem of the Day - [<a href="https://leetcode.com/problems/bulb-switcher/"> 319. Bulb Switcher </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int bulbSwitch(int n) {
    long left = 1;
    long right = n;
    long result = 0;

    while (left <= right) {
        long mid = left + (right - left) / 2;
        long square = mid * mid;

        if (square == n) {
            return (int)mid;
        } else if (square < n) {
            left = mid + 1;
            result = mid;
        } else {
            right = mid - 1;
        }
    }

    return (int)result;
}
</pre>
