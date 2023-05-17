## Problem of the Day - [<a href="https://leetcode.com/problems/maximum-twin-sum-of-a-linked-list/"> 2130. Maximum Twin Sum of a Linked List </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int pairSum(ListNode* head) {
        ListNode* slow = head;
        ListNode* fast = head;
        int maxVal = 0;

        while(fast && fast -> next)
        {
            slow = slow -> next;
            fast = fast -> next -> next;
        }

        ListNode *nextNode, *prev = NULL;
        while (slow) {
            nextNode = slow->next;
            slow->next = prev;
            prev = slow;
            slow = nextNode;
        }

        while(prev)
        {
            maxVal = max(maxVal, head -> val + prev -> val);
            prev = prev -> next;
            head = head -> next;
        }

        return maxVal;
    }
</pre>
