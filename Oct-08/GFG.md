### Problem of the Day : [Insert in a Sorted List](https://practice.geeksforgeeks.org/problems/insert-in-a-sorted-list/1)

#### Solution :
<pre>
  Node *sortedInsert(struct Node* head, int data) {
        Node* newNode = new Node(data);
        if (head == nullptr || data < head->data) {
            newNode->next = head;
            return newNode;
        }
        
        Node* current = head;
        while (current->next != nullptr && current->next->data < data) 
            current = current->next;
        
        newNode->next = current->next;
        current->next = newNode;
        return head;
    }
</pre>
