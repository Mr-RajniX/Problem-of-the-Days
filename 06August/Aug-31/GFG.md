### Problem of the Day : [AVL Tree Deletion](https://practice.geeksforgeeks.org/problems/avl-tree-deletion/1)

#### Solution :
<pre>
  int NodeHeight(Node* p)
{
    int hl=0, hr=0;
    hl = p&&p->left?p->left->height:0;
    hr = p&&p->right?p->right->height:0;
    return (hl>hr?hl+1:hr+1);
}

int BalanceFactor(Node* p)
{
    // hl-hr
    int hl=0, hr=0;
    hl = p&&p->left?p->left->height:0;
    hr = p&&p->right?p->right->height:0;
    
    return (hl-hr);
}

Node* LLRotate(Node* p)
{
    Node* pl = p->left;
    Node* plr = pl->right;
    
    pl->right = p;
    p->left = plr;
    
    p->height = NodeHeight(p);
    pl->height = NodeHeight(pl);
    
    return pl;
}

Node* LRRotate(Node* p)
{
    Node* pl = p->left;
    Node* plr = pl->right;
    
    pl->right = plr->left;
    p->left = plr->right;
    
    plr->left = pl;
    plr->right = p;
    
    p->height = NodeHeight(p);
    pl->height = NodeHeight(pl);
    plr->height = NodeHeight(plr);
    
    return plr;
}

Node* RRRotate(Node* p)
{
    Node* pr = p->right;
    Node* prl = pr->left;
    
    pr->left = p;
    p->right = prl;
    
    p->height = NodeHeight(p);
    pr->height = NodeHeight(pr);
    
    return pr;
}

Node* RLRotate(Node* p)
{
    Node* pr = p->right;
    Node* prl = pr->left;
    
    p->right = prl->left;
    pr->left = prl->right;
    
    prl->left = p;
    prl->right = pr;
    
    p->height = NodeHeight(p);
    pr->height = NodeHeight(pr);
    prl->height = NodeHeight(prl);
    
    return prl;
}

Node* InSuccessor(Node* p)
{
    while(p && p->left)
    {
        p=p->left;
    }
    return p;
}

Node* InPredecessor(Node* p)
{
    while(p && p->right)
    p=p->right;
    return p;
}


Node* deleteNode(Node* root, int data)
{
    if(root==NULL) return NULL;
    if(root->left==NULL && root->right==NULL)
    {
        if(data==root->data)
        {
            free(root);
            return NULL;
        }
    }
    
    if(data<root->data)
    root->left = deleteNode(root->left,data);
    else if(data>root->data)
    root->right = deleteNode(root->right,data);
    else
    {
        if(root->right!=NULL)
        {
            // successor
            Node* q = InSuccessor(root->right);
            root->data = q->data;
            root->right = deleteNode(root->right, q->data);
        }
        else
        {
            // Predecessor
            Node* q = InPredecessor(root->left);
            root->data = q->data;
            root->left = deleteNode(root->left,q->data);
        }
    }
    root->height = NodeHeight(root);
    if(BalanceFactor(root)==2 && BalanceFactor(root->left)==1)
    return LLRotate(root);
    else if(BalanceFactor(root)==2&&BalanceFactor(root->left)==-1)
    return LRRotate(root);
    else if(BalanceFactor(root)==2&&BalanceFactor(root->left)==0)
    return LLRotate(root);
    else if(BalanceFactor(root)==-2&&BalanceFactor(root->right)==1)
    return RLRotate(root);
    else if(BalanceFactor(root)==-2&&BalanceFactor(root->right)==-1)
    return RRRotate(root);
    else if(BalanceFactor(root)==-2&&BalanceFactor(root->right)==0)
    return RRRotate(root);
    
    return root;
}
</pre>
