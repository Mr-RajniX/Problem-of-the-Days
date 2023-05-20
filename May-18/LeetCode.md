## Problem of the Day - [<a href="https://leetcode.com/problems/minimum-number-of-vertices-to-reach-all-nodes/"> 1557. Minimum Number of Vertices to Reach All Nodes </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   vector<int> findSmallestSetOfVertices(int n, vector<vector<int>>& edges) {
         vector<int> res, visited(n); 
        for (auto& e: edges)
            visited[e[1]] = 1;
        for (int i = 0; i < n; ++i)
            if (visited[i] == 0)
                res.push_back(i);                
        return res;
        
    }
</pre>
