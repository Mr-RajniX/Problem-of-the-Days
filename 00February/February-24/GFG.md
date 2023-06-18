## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/e7d81a082cda6bd1e959d943197aa3bc21b88bdb/1"> Shortest Path Using Atmost One Curved Edge </a>]


#### ⭐<ins>Solution Function Code</ins> -

    vector<int> dijkstra(int u, int b, int n, vector<pair<int,int>> adj[]) {
        vector<int> dis;
        dis.assign(n+1, 1000000000);
        priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>>> pq;
        dis[u] = 0;
        pq.push({0, u});
        while(!pq.empty()) {
            int u = pq.top().second;
            pq.pop();
            for(auto p: adj[u]) {
                  int v = p.first;
                  int w = p.second;
                  if(dis[v] > dis[u] + w) {
                        dis[v] = dis[u] + w;
                        pq.push({dis[v], v});
                  }
            }
        }
        return dis;
    }

    int shortestPath(int n, int m, int a, int b, vector<vector<int>> edges) {
        vector<pair<int,int>> adj[n+1];
        vector<vector<int>> curved;
        for(int i=0; i<m; i++){
            int u = edges[i][0];
            int v = edges[i][1];
            int w = edges[i][2];
            int cw = edges[i][3];
            adj[u].push_back({v, w});
            adj[v].push_back({u, w});
            curved.push_back({u, v, cw});
        }
        vector<int> da = dijkstra(a, b, n, adj);
        vector<int> db = dijkstra(b, a, n, adj);
        int ans = da[b];
        for(int i=0; i<m; i++){
            int u = curved[i][0];
            int v = curved[i][1];
            int cw = curved[i][2];
            ans = min(ans, da[u] + cw + db[v]);
            ans = min(ans, da[v] + cw + db[u]);
        }
        if(ans>=1000000000) return -1;
        return ans;
    }

