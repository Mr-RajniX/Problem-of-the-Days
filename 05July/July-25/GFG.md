### Problem of the Day : [Level order traversal in spiral form](https://practice.geeksforgeeks.org/problems/level-order-traversal-in-spiral-form/1)

#### Solution :
<pre>
  vector< int > findSpiral(Node *root)
  {
    vector< int > ans;
    queue< Node* > q;
    q.push(root);
      
    int l=1;
    while(!q.empty()){
        int n=q.size();
        for(int i=0;i < n;i++){
            ans.push_back(q.front()->data);
            if(q.front()->left)q.push(q.front()->left);
            if(q.front()->right)q.push(q.front()->right);
            q.pop();
        }
        if(l%2) 
            reverse(ans.rbegin(),ans.rbegin()+n);
        l++;
    }
    return ans;
}
</pre>
