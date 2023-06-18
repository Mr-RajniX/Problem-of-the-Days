## Problem of the Day - [<a href="https://leetcode.com/problems/find-the-longest-valid-obstacle-course-at-each-position/"> 1964. Find the Longest Valid Obstacle Course at Each Position </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   vector<int> longestObstacleCourseAtEachPosition(vector<int>& obstacles) {
        vector<int> v(obstacles.size(),(int)1e9), ans;
        for(int x: obstacles){
            auto ub = upper_bound(begin(v), end(v), x);
            ans.emplace_back(ub - v.begin() + 1);
            *ub = x;
        }
        return ans;
    }
</pre>

#### ⭐<ins>Solution Function Code #2</ins> -
<pre>

   vector<int> longestObstacleCourseAtEachPosition(vector<int>& obstacles) {
        vector<int> ans;
        vector<int> dp;
        for (int i = 0; i < obstacles.size(); i++) {
            int len = lower_bound(dp.begin(), dp.end(), obstacles[i] + 1) - dp.begin();
            if (len == dp.size()) {
                dp.push_back(obstacles[i]);
            } else {
                dp[len] = obstacles[i];
            }
            ans.push_back(len + 1);
        }
        return ans;
    }
</pre>
