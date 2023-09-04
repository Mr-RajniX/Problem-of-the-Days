### Problem of the Day : [141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)

#### Solution :
<pre>
  bool hasCycle(ListNode *head) {
        ListNode *first = head;
        ListNode *second = head;
        while(first != nullptr && first -> next != nullptr){
            first = first->next->next;
            second = second->next;
            if(first == second) return true;
        }return false;
    }
</pre>
