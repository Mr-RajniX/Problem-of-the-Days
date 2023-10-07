### Problem of the Day : [Pairwise swap elements of a linked list](https://practice.geeksforgeeks.org/problems/pairwise-swap-elements-of-a-linked-list-by-swapping-data/1)

#### Solution :
<pre>
  Node* pairWiseSwap(struct Node* head) {
        if(head==NULL || head->next==nullptr)
            return head;
            
        Node* first = head;
        Node* second = head->next;
        Node* new_head = pairWiseSwap(head->next->next);
        
        second->next = first;
        first->next = new_head;
        return second;
    }
</pre>
