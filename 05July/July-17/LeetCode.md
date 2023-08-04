### Problem of the Day : [445. Add Two Numbers II](https://leetcode.com/problems/add-two-numbers-ii/)

#### Solution : using STACK
<pre>
  ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        stack<int> s1, s2;
        while(l1 != nullptr){
            s1.push(l1->val); l1 = l1->next;
        }while(l2 != nullptr){
            s2.push(l2->val); l2 = l2->next;
        }

        ListNode* ans = nullptr;
        int extra = 0;

        while(!s1.empty() || !s2.empty() || extra != 0){
            int digit1 = !s1.empty() ? s1.top() : 0;
            int digit2 = !s2.empty() ? s2.top() : 0;

            int sum = digit1 + digit2 + extra;
            int digit = sum % 10;
            extra = sum / 10;

            ListNode* newnode = new ListNode(digit);
            newnode->next = ans;
            ans = newnode;

            if( !s1.empty()) s1.pop();
            if( !s2.empty()) s2.pop();
        } return ans;
    }
</pre>
#### Solution #2 : Using Reverse Linked List :) Do it your own.
<pre>
  ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        l1 = Reverse(l1);
        l2 = Reverse(l2);
        ListNode* ans =  Add(l1,l2);
        return Reverse(ans);
    }
    ListNode* Reverse(ListNode* head){
        ListNode* prev = NULL;
        while(head){
            ListNode* go = head->next;
            head->next = prev;
            prev = head;
            head = go;
        } return prev;
    }
    ListNode* Add(ListNode* l1, ListNode* l2){
        ListNode* dummy =  new ListNode(0);//IT IS A TEMPORARY HEAD
        ListNode* tail = dummy;
        int carry = 0;
        while(l1 != nullptr || l2 != nullptr || carry != 0){
            int digit1 = (l1 != nullptr) ? l1->val : 0;
            int digit2 = (l2 != nullptr) ? l2->val : 0;

            int sum = digit1 + digit2 + carry;
            int digit = sum % 10;
            carry = sum / 10;

            ListNode* newnode = new ListNode(digit);
            tail->next = newnode;
            tail = tail->next;
            l1 = (l1 != nullptr) ? l1->next : nullptr;
            l2 = (l2 != nullptr) ? l2->next : nullptr;
        }
        ListNode* result = dummy->next;
        delete dummy;
        return result;
    }
</pre>
