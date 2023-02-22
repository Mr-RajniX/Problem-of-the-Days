## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/95423710beef46bd66f8dbb48c510b2c320dab05/1"> Connect Nodes at Same Level </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    void connect(Node *root)
    {
       queue<Node*> queue;
        queue.push(root);
        while(!queue.empty()){
            int n = queue.size();
            Node* prev = NULL;
            for(int i = 1 ; i <= n ; i++){
                Node* cur = queue.front();
                queue.pop();
                cur->nextRight = prev;
                if(cur->right) queue.push(cur->right);
                if(cur->left) queue.push(cur->left);
                prev = cur;
            }
        }
    }
</pre>
