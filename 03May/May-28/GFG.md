## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/nth-node-from-end-of-linked-list/1"> Nth node from end of linked list </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int getNthFromLast(Node *head, int n){
        if(head==NULL)
            return -1;
        struct Node *temp=head;
        int cnt=0;
        while(temp!=NULL){
            temp=temp->next;
            cnt++;
        }
        if(n>cnt)
            return -1;
        int pos=cnt-n;
        temp=head;
        while(pos){
            temp=temp->next;
            pos--;
        }
        return temp->data;
    }
</pre>
