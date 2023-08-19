### Problem of the day : [1489. Find Critical and Pseudo-Critical Edges in Minimum Spanning Tree](https://leetcode.com/problems/find-critical-and-pseudo-critical-edges-in-minimum-spanning-tree/)

#### Solution :
<pre>
  class UnionFind {
public:
    vector < int > parent;
    UnionFind(int n) {
        parent.resize(n);
        for (int i = 0; i < n; i++)
            parent[i] = i;
    }
    int findParent(int p) {
        return parent[p] == p ? p : parent[p] = findParent(parent[p]);
    }
    void Union(int u, int v) {
        int pu = findParent(u), pv = findParent(v);
        parent[pu] = pv;
    }
};
                            </pre>
`> main solution program :`
<pre>
class Solution {
private:
    int MST(int &n, vector < vector < int > > &edges, int block, int e) {
        UnionFind uf(n);
        int w = 0;
        if (e != -1) {
            w += edges[e][2]; 
            uf.Union(edges[e][0], edges[e][1]); 
        }
        for (int i = 0; i < edges.size(); i++) {
            if (i == block) continue; 
            if (uf.findParent(edges[i][0]) == uf.findParent(edges[i][1])) continue;

            uf.Union(edges[i][0], edges[i][1]);
            w += edges[i][2]; 
        }
        for (int i = 0; i < n; i++) 
            if (uf.findParent(i) != uf.findParent(0)) 
                return INT_MAX;
        return w;
    }

public:
    static bool cmp(vector < int > &a, vector < int > &b) {
        return a[2] < b[2]; 
    }

    vector < vector < int > > findCriticalAndPseudoCriticalEdges(int n, vector < vector < int > > &edges) {
        vector < int > c, psc;
        for (int i = 0; i < edges.size(); i++) {
            edges[i].push_back(i);
        }

        sort(edges.begin(), edges.end(), cmp);
        int mst = MST(n, edges, -1, -1);
        for (int i = 0; i < edges.size(); i++) {
            if (mst < MST(n, edges, i, -1)) 
                c.push_back(edges[i][3]);
            else if (mst == MST(n, edges, -1, i)) 
                psc.push_back(edges[i][3]);
        }
        return {c, psc};
    }
};
</pre>
