## Problem of the Day - [<a href="https://leetcode.com/problems/linked-list-cycle-ii/description/"> 142. Linked List Cycle II </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    ListNode* detectCycle(ListNode* head) {
    ListNode* slow = head;
    ListNode* fast = head;
    while (fast && fast->next) {
      slow = slow->next;
      fast = fast->next->next;
      if (slow == fast) {
        slow = head;
        while (slow != fast) {
          slow = slow->next;
          fast = fast->next;
        }
        return slow;
      }
    }
    return nullptr;
  
    }
</pre>
