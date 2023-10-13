#### Problem of the Day : [746. Min Cost Climbing Stairs](https://leetcode.com/problems/min-cost-climbing-stairs/)

#### Solution :
<pre>
  int minCostClimbingStairs(vector< int>& cost) {        
        for (int i = cost.size()-3; i >= 0; i--)
            cost[i] += min(cost[i+1], cost[i+2]);
        return min(cost[0], cost[1]);
    }
</pre>
