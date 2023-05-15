## Problem of the Day - [<a href="https://leetcode.com/problems/swapping-nodes-in-a-linked-list/"> 1721. Swapping Nodes in a Linked List </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   ListNode* swapNodes(ListNode* head, int k) {
        ListNode *left_ptr = head, *right_ptr = head;
        for (int i = 0; i < k-1; i++) {
            right_ptr = right_ptr->next;
        }        
        ListNode *end_ptr = right_ptr;
        while (right_ptr->next) {
            left_ptr = left_ptr->next;
            right_ptr = right_ptr->next;
        }        
        swap(end_ptr->val, left_ptr->val);        
        return head;
    }
</pre>
