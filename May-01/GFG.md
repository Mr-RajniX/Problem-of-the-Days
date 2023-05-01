## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/079dee7e7db7a784ed73f604e3cf1712432edf79/1"> Subtree In N-ary Tree </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   string dfs(Node* root,unordered_map<string,int> &ump,int &ans){
         if(!root){
             return "#";
         }
        string str="";
        for(auto x:root->children){
            str += dfs(x,ump,ans) + ',';
        }
         string s = str + to_string(root->data);
         if(ump[s]==1){
             ans++;
         }
         ump[s]++;
         return s;
    }
    int duplicateSubtreeNaryTree(Node *root){
        // Code here
        int ans=0;
        unordered_map<string,int> ump;
        dfs(root,ump,ans);
        return ans;
    }
</pre>
