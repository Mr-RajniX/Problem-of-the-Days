### Problem of the Day : [Delete nodes having greater value on right](https://practice.geeksforgeeks.org/problems/delete-nodes-having-greater-value-on-right/1)

#### Solution :
<pre>
  Node *compute(Node *head){
        Node* curr=head;
        Node* prev=NULL;
        while(curr->next!=NULL){
            Node* temp=curr->next;
            while(temp->next!=NULL && temp->data<=curr->data){
                temp=temp->next;
            }
            if(temp->data>curr->data){
                if(prev==NULL){
                    curr->next=NULL;
                    curr=temp;
                    head=temp;
                }
                else{
                    prev->next=temp;
                    curr->next=NULL;
                    curr=temp;
                }
            }
            else{
                prev=curr;
                curr=curr->next;
            }
        }
        return head;
    }
</pre>
