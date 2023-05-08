## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/d064cc0468a5c2bb7817ecd7c1bc59ce25e23613/1"> Minimum BST Sum Subtree </a>]


#### ⭐<ins>Solution Function Code </ins> -
<pre>

    bool isBst(Node* root,int &prev,int &sum,int &cnt){
        if(root==NULL){
            return  true;
        }
       if( !isBst(root->left,prev,sum,cnt)){
           return false;
       }
        if(prev>=root->data){
            return false;
        }
        sum+=root->data;
        cnt++;
        prev=root->data;
        return isBst(root->right,prev,sum,cnt);
       return true;
    }
    void dfs(Node *root,int target,int &ans){
        if(root==NULL){
            return;
        }
        int sum=0;
        int cnt=0;
        int prev=-1;
        if(isBst(root,prev,sum,cnt)){
            if(sum==target){
                ans=min(ans,cnt);
            }
        }
        dfs(root->left,target,ans);
        
        dfs(root->right,target,ans);
        
    }
    int minSubtreeSumBST(int target, Node *root) {
        // code here
        int ans=INT_MAX;
        dfs(root,target,ans);
        return ans==INT_MAX?-1:ans;
    }
</pre>
