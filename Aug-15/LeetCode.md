# Happy Independence Day <img src="https://em-content.zobj.net/thumbs/72/google/350/flag-india_1f1ee-1f1f3.png" width=40>
### Problem of the Day : [86. Partition List](https://leetcode.com/problems/partition-list/)

#### Solution : 
<pre>
  ListNode* partition(ListNode* head, int x) {
        ListNode before(0), after(0);
        ListNode* beforeCurrent = &before;
        ListNode* afterCurrent = &after;

        while(head){
            if( head -> val < x){
                beforeCurrent -> next = head;
                beforeCurrent = head;
            }else{
                afterCurrent -> next = head;
                afterCurrent = head;
            }
            head = head -> next;
        }
        afterCurrent -> next = nullptr;
        beforeCurrent -> next = after.next;
        return before.next;
    }
</pre>
