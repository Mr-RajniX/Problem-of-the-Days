### Problem of the Day : [Reverse a Linked List in groups of given size](https://practice.geeksforgeeks.org/problems/reverse-a-linked-list-in-groups-of-given-size/1)

#### Solution :
<pre>
  struct node *reverse (struct node *head, int k){ 
        node *current = head;
        node *prev = NULL;
        node *next = NULL;
        int count =0;
        while(current != NULL && count < k){
            next = current->next;
            current->next = prev;
            prev = current;
            current = next;
            count++;
        }
        if(next != NULL){
            head->next = reverse(next,k);
        }
        return prev;
    }
</pre>
