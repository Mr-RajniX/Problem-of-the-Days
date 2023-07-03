## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/union-of-two-linked-list/1"> Union of Two Linked Lists </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  struct Node* makeUnion(struct Node* head1, struct Node* head2)
    {
        set<int>my;
        Node *temp1,*temp2;
        temp1=head1;
        temp2=head2;
        while(temp1!=NULL)
        {
            my.insert(temp1->data);
            temp1=temp1->next;
        }
        
        while(temp2!=NULL)
        {
            my.insert(temp2->data);
            temp2=temp2->next;
        }
        
        Node *head,*last;
        head=new Node(0);
        last=head;
        for(auto it:my)
        {
            Node *t;
            t= new Node(it);
            last->next=t;
            last=t;
        }
        
        head=head->next;
        return head;
    }
</pre>
