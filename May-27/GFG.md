## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/modify-linked-list-1-0546/1"> Modify Linked List-1 </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  struct Node* modifyTheList(struct Node *head){
        Node *r=head;
        Node* dummy=new Node(0);
        Node *l=dummy,*prev=NULL,*temp;
        int n=0;
        while(r!=NULL) {
            dummy->next=new Node(r->data);
            dummy=dummy->next;
            r=r->next;
            n++;
        }
        l=l->next;
        while(l!=NULL) {
            temp=l->next;
            l->next=prev;
            prev=l;
            l=temp;
        }
        int t=n/2;
        Node* head2=prev;
        while(t--) {
            prev->data=prev->data-head->data;
            prev=prev->next;
            head=head->next;
        }
        return head2;
    }
</pre>
