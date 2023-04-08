## Problem of the Day - [<a href="https://leetcode.com/problems/clone-graph/description/"> 133. Clone Graph </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    unordered_map<Node*,Node*> mp;
    void  dfs(Node* node){
        Node* copy=new Node(node->val);
        mp[node]=copy;
        for(auto ng: node->neighbors){
            if(mp.find(ng)!=mp.end()){
                copy->neighbors.push_back(mp[ng]);
            }else{
                dfs(ng);
                copy->neighbors.push_back(mp[ng]);
            }
        }
    }
    Node* cloneGraph(Node* node) {
        if(node==NULL) return NULL;
        dfs(node);
       return mp[node];
    }
</pre>
