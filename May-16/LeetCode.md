## Problem of the Day - [<a href="https://leetcode.com/problems/swap-nodes-in-pairs/"> 24. Swap Nodes in Pairs </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    ListNode* swapPairs(ListNode* head) {
        if (!head or !head->next)
            return head;

        ListNode *dummyHead = new ListNode(-1);
        dummyHead->next = head;
        head = dummyHead;

        ListNode *dummyTail = new ListNode(-1);
        ListNode *ptr = head;
        while (ptr->next)
            ptr = ptr->next;
        ptr->next = dummyTail;

        ListNode *prev = head, *cur = head->next, *next = head->next->next;
        while (next and next->val != -1)
        {
            ListNode *nextCur = next->next;
            prev->next = next; 
            cur->next = next->next; 
            next->next = cur;

            prev = cur; 
            cur = nextCur; 
            next = cur->next; 
        }   
        ListNode *remove = head;
        while(remove->next->val != -1)
            remove = remove->next;
        remove->next = NULL;
        return head = head->next;
    }
</pre>
