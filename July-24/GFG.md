### Problem of the Day : [Right View of Binary Tree](https://practice.geeksforgeeks.org/problems/right-view-of-binary-tree/1)

#### Solution :
<pre>
  vector< int > rightView(Node *root){
       vector< int > ans;
       queue< Node* > qu;
       qu.push(root);
       while(!qu.empty()) {
           int n = qu.size();
           for(int i = 0; i<n; i++) {
               Node * node = qu.front();
               qu.pop();
               if(i == n-1) ans.push_back(node->data);
               if(node->left) qu.push(node->left);
               if(node->right) qu.push(node->right);
           }
       }
       return ans;
    }
</pre>
