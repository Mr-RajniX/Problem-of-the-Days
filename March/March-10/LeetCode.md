## Problem of the Day - [<a href="https://leetcode.com/problems/linked-list-random-node/description/"> 382. Linked List Random Node </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    vector<ListNode*> nodes;
    Solution(ListNode* head) {
        while(head!=NULL){
            nodes.push_back(head);
            head=head->next;
        }
    }    
    int getRandom() {
      int n=nodes.size();
      int radn=rand()%n;
      return nodes[radn]->val;  
    }
</pre>
