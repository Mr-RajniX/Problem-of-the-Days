## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/bae68b4d6a2a77fb6bd459cf7447240919ebfbf5/1"> Reverse both parts </a>]


#### ⭐<ins>Solution Function Code</ins> -


    Node *reverse(Node *head, int k){
        Node *curr,*prev,*h;
        curr=head;
        prev=NULL;
        while(k--){
            Node *t=curr->next;
            curr->next=prev;
            prev=curr;
            curr=t;
        }
        h=prev;
        prev=NULL;
        while(curr){
            Node *t=curr->next;
            curr->next=prev;
            prev=curr;
            curr=t;
        }
        head->next=prev;
        return h;
    }
