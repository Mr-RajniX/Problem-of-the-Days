### Problem of the Day : [435. Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/)

#### Solution :
<pre>
    static bool cmp(vector< int >& a, vector< int >& b){
        return a[1] < b[1];
    }
    int eraseOverlapIntervals(vector< vector< int >>& intervals) {
        int n = intervals.size();
        sort(intervals.begin(), intervals.end(), cmp);

        int prev = 0;
        int count = 1;

        for(int i = 1; i < n; i++){
            if(intervals[i][0] >= intervals[prev][1]){
                prev = i;
                count++;
            }
        }
        return n - count;
    }
</pre>
