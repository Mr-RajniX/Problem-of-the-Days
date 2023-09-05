### Problem of the Day : [138. Copy List with Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer/)

#### Solution :
<pre>
  Node* copyRandomList(Node* head) {
        if (!head) return nullptr;
        
        unordered_map < Node*, Node*> old_to_new;
        
        Node* curr = head;
        while (curr) {
            old_to_new[curr] = new Node(curr->val);
            curr = curr->next;
        }
        
        curr = head;
        while (curr) {
            old_to_new[curr]->next = old_to_new[curr->next];
            old_to_new[curr]->random = old_to_new[curr->random];
            curr = curr->next;
        }
        
        return old_to_new[head];
    }
</pre>
