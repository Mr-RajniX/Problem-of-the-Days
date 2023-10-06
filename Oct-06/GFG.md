### Problem of the Day : [Reverse alternate nodes in Link List](https://practice.geeksforgeeks.org/problems/given-a-linked-list-reverse-alternate-nodes-and-append-at-the-end/1)

#### Solution :
<pre>
  void rearrange(struct Node *odd){
         if(odd->next == NULL) return;
        Node *od = odd, *pr = NULL, *r, *p, *nxt;    
        while(od != NULL && od->next != NULL){
            nxt = od->next->next;
            r = od->next;
            r->next = pr;
            pr = r;
            p = od;
            od->next = nxt;
            od = od->next;
            
        }
        if(!od) od = p;
        od ->next = r;
    }
</pre>
