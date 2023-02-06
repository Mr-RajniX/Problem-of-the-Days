## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/c85e3a573a7de6dfd18398def16d05387852b319/1"> BST Downward Traversal </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    class Solution{
public:
    bool flag=false;
    long long ans=0,g;
    Node *start=NULL;
    void dfs(Node* root,int trt,int gg)
    {
        if(root==NULL)return;
        if(root->data==trt && !flag)
        {
            g=gg;
            start=root;
            return;
            
        }
        dfs(root->left,trt,gg-1);
        dfs(root->right,trt,gg+1);
        if(flag)
        {
            if(g==gg)ans+=root->data;
        }
    }
    long long int verticallyDownBST(Node *root,int target){
        dfs(root,target,0);
        flag=true;
        if(start==NULL)return -1;
        dfs(start,target,g);
        return ans-start->data;
    }
};
</pre>
