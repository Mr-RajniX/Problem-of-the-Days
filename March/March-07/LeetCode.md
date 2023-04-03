## Problem of the Day - [<a href="https://leetcode.com/problems/minimum-time-to-complete-trips/description/"> 2187. Minimum Time to Complete Trips </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    bool isValid(vector<int>& time, long mid, int totalTrips){
        long finish = 0;
        for (int each : time) {
            finish += mid / each;
            if (finish >= totalTrips) { return true; }
        }
        return false;
    }
    long long minimumTime(vector<int>& time, int totalTrips) {
        long result = 0;
        long low = 1;
        long high = 100000000000000L;
        while (low <= high) {
            long mid = low + (high - low) / 2;
            bool pass = isValid(time, mid, totalTrips);            
            if (pass) {  
                result = mid;
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }
        return result;
    }
</pre>
