## Problem of the Day - [<a href="https://leetcode.com/problems/remove-max-number-of-edges-to-keep-graph-fully-traversable/"> 1579. Remove Max Number of Edges to Keep Graph Fully Traversable </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   class UnionFind {
private:
    vector<int> parent;
    int groups;

public:
    UnionFind(int n) : parent(n + 1), groups(n) {
        iota(parent.begin(), parent.end(), 0);
    }
    int union_(int u, int v) {
        const int uParent = find_(u);
        const int vParent = find_(v);
        if (uParent == vParent)
            return 0;
        parent[uParent] = vParent;
        --groups;
        return 1;
    }
    int find_(int v) {
        if (parent[v] != v)
            parent[v] = find_(parent[v]);
        return parent[v];
    }
    bool is_united() {
        return groups == 1;
    }
};
class Solution {
private:
    static constexpr int 
        TYPE = 0, U = 1, V =2,
        ALICE = 1, BOB = 2, BOTH = 3;
public:
    int maxNumEdgesToRemove(int n, vector<vector<int>>& edges) {
        for (int i = 0, j = edges.size() - 1; i < j; ) {
            if (edges[i][TYPE] == BOTH) {
                ++i;
                continue;
            }
            swap(edges[i], edges[j]);
            --j;
        }
        UnionFind alice_uf(n), bob_uf(n);
        int added = 0;
        for (const auto& edge : edges) {
            const int type = edge[TYPE];
            const int u = edge[U];
            const int v = edge[V];
            added += (type == BOTH) ? 
                alice_uf.union_(u, v) | bob_uf.union_(u, v) :
                (type == ALICE) ? alice_uf.union_(u, v) : bob_uf.union_(u, v);
            if (alice_uf.is_united() && bob_uf.is_united())
                return edges.size() - added;
        }
        if (alice_uf.is_united() && bob_uf.is_united())
            return edges.size() - added;
        return -1;
    }
};
</pre>
