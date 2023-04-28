## Problem of the Day - [<a href="https://leetcode.com/problems/similar-string-groups/"> 839. Similar String Groups </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int findParent(vector<int>&parent, int node)
    {
        if (parent[node] == node) return node;
        else return findParent(parent, parent[node]);
    }
    bool merge(vector<int>&parent, int node1, int node2)
    {
        int parent1 = findParent(parent, node1);
        int parent2 = findParent(parent, node2);
        if (parent1 == parent2) return false;
        
        parent[parent1] = parent2; 
        return true;
    }
    bool isSimilar(string& s1, string& s2)
    {
        int different = 0;
        for (int i = 0; i < s1.size(); i++)
        {
            if (s1[i] != s2[i]) different++;
        }
        return (different == 0 || different == 2);
    }
    int numSimilarGroups(vector<string>& strs) 
    {
        int n = strs.size();
        vector<int>parent(n);
        int componentCount = n;
        for (int i = 0; i < n; i++) parent[i] = i;
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                if (isSimilar(strs[i], strs[j]))
                {
                    bool hasMerged = merge(parent, i, j);
                    if (hasMerged) componentCount--;
                }
            }
        }
        return componentCount;
    }
</pre>
