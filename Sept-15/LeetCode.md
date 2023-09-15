### Problem of the Day : [1584. Min Cost to Connect All Points](https://leetcode.com/problems/min-cost-to-connect-all-points/)

#### Solution :
<pre>
  int minCostConnectPoints(vector< vector< int >>& points) {
        int n = points.size();
        int min_cost = 0;
        vector< bool > visited(n, false);
        priority_queue< pair< int, int >, std::vector< pair<int, int >>, greater< pair< int, int >>> pq; 
        unordered_map< int, int > cache;
        pq.push({0, 0});

        while (!pq.empty()) {
            auto edge = pq.top();
            pq.pop();
            int cost = edge.first;
            int u = edge.second;

            if (visited[u]) {
                continue;
            }

            visited[u] = true;
            min_cost += cost;

            for (int v = 0; v < n; v++) {
                if (!visited[v]) {
                    int dist = abs(points[u][0] - points[v][0]) + abs(points[u][1] - points[v][1]);
                    if (cache.find(v) == cache.end() || dist < cache[v]) {
                        cache[v] = dist;
                        pq.push({dist, v});
                    }
                }
            }
        }

        return min_cost;
    }
</pre>
