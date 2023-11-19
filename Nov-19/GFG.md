#### Problem of the Day : [Intersection of two sorted Linked lists](https://www.geeksforgeeks.org/problems/intersection-of-two-sorted-linked-lists/1)

#### Solution :
<pre>
  Node* findIntersection(Node* head1, Node* head2)
    {
        Node *ptr = head1;
        Node *ptr1 = head2;
        unordered_map<int, int> mp;
        while(ptr!=nullptr){
            mp[ptr->data]++;
            ptr=ptr->next;
        }
        vector<int> v;
        while(ptr1!=nullptr){
            if (mp.find(ptr1->data)!=mp.end() and mp[ptr1->data]>0) {
                v.push_back(ptr1->data);
                mp[ptr1->data]--;
            }
            ptr1=ptr1->next;
        }
        if (v.size()==0) return NULL;
        Node *np;
        np = new Node(v[0]);
        Node *pp = np;
        for(int i=1; i<v.size(); i++){
            Node *nn; 
            nn = new Node(v[i]);
            pp->next=nn;
            pp=nn;
        }
        return np;
    }
</pre>
