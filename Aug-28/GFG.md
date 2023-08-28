### Problem of the Day : [Remove duplicate element from sorted Linked List](https://practice.geeksforgeeks.org/problems/remove-duplicate-element-from-sorted-linked-list/1)

#### Solution :
<pre>
  Node *removeDuplicates(Node *head){
    Node *temp = head;
    while(temp->next != NULL){
        while(temp->data == temp->next->data){
            temp->next = temp->next->next;
            if(temp->next == NULL){
                return head;
            }
        }
        temp = temp->next;
    }
    return head;
}
</pre>
