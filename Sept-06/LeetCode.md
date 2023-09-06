### Problem of the Day : [725. Split Linked List in Parts](https://leetcode.com/problems/split-linked-list-in-parts/)

#### Solution :
<pre>
  vector< ListNode*> splitListToParts(ListNode* head, int k) {
        vector< ListNode*> part(k, nullptr);
        int len = 0;
        for (ListNode* node = head; node; node = node->next)
            len++;
        int n = len / k, r = len % k;

        ListNode* node = head, *prev = nullptr;

        for (int i = 0; node && i < k; i++, r--) {
            part[i] = node;
            for (int j = 0; j < n + (r > 0); j++) {
                prev = node;
                node = node->next;
            }
            prev->next = nullptr;
        }
        return part;
    }
</pre>
