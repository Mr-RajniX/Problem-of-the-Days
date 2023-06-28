## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/maximum-depth-of-binary-tree/1"> Maximum Depth Of Binary Tree </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>
  int maxDepth(Node *root) {
        int count=0;
        return count = solve(0,0,root);
    }
    int solve(int count1,int count2, Node* root){
        if(root==nullptr){
            return 0;
        }
        count1 = 1+solve(count1,count2,root->left);
        count2 = 1+solve(count1,count2,root->right);
        return max(count1,count2);
    }
</pre>
