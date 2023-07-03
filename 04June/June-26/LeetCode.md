## Problem of the Day - [<a href="https://leetcode.com/problems/total-cost-to-hire-k-workers/"> 2462. Total Cost to Hire K Workers </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  long long totalCost(vector< int >& costs, int k, int candidates) {
        int i = 0;
        int j = costs.size() - 1;
        priority_queue< int, vector< int >, greater< int >> pq1;
        priority_queue< int, vector< int >, greater< int >> pq2;

        long long ans = 0;
        while(k--){
            while(pq1.size() < candidates && i <= j){
                pq1.push(costs[i++]);
            }
            while(pq2.size() < candidates && i <= j){
                pq2.push(costs[j--]);
            }

            int t1 = pq1.size() > 0 ? pq1.top() : INT_MAX;
            int t2 = pq2.size() > 0 ? pq2.top() : INT_MAX;

            if(t1 <= t2){
                ans += t1;
                pq1.pop();
            }
            else{
                ans += t2;
                pq2.pop();
            }
        }
        return ans;
    }
</pre>
