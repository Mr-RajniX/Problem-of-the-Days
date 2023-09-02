### Problem of the Day : [Delete a Node in Single Linked List](https://practice.geeksforgeeks.org/problems/delete-a-node-in-single-linked-list/1)

#### Solution :
<pre>
  Node* deleteNode(Node *head,int x){
    Node*temp=head;
    if(x==1)  return temp->next;
    while(x-->2){    
        temp=temp->next;
    }
    temp->next=temp->next->next;
    return head;
}
</pre>
