## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/4b7ff87c26ed23b3f63c25c611690213d44fb6aa/1"> Max Level Sum in Binary Tree </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int maxLevelSum(Node* root) {
        // Your code here
        queue<Node *> q;
        q.push(root);
        q.push(NULL);
        int sum = 0;
        int maxSum = INT_MIN;
        while(!q.empty()){
            Node *cur = q.front();
            q.pop();
            if(cur == NULL){
                if(q.empty()){
                    return max(sum, maxSum);
                }else{
                    maxSum = max(sum, maxSum);
                    sum = 0;
                    q.push(NULL);
                }
            }else{
                sum += cur -> data;
                if(cur -> left != NULL){
                    q.push(cur -> left);
                }
                if(cur -> right != NULL){
                    q.push(cur -> right);
                }
            }
        }
        return max(sum, maxSum);
    }
</pre>
