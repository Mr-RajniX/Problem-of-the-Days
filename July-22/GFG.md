### Problem of the  Day :[Remove duplicates from an unsorted linked list](https://practice.geeksforgeeks.org/problems/remove-duplicates-from-an-unsorted-linked-list/1)

#### Solution :
<pre>
  Node * removeDuplicates( Node *head) {
     if(head==NULL or head->next==NULL)return head;
      Node*dummy=new Node(-1);
      Node*prev=dummy,*temp=NULL,*curr=head;
      prev->next=head;
      unordered_set<int>st;
      while(curr){
          if(st.find(curr->data)==st.end()){
              st.insert(curr->data);
              prev=curr;
          }
          else{
              prev->next=curr->next;
          }
          curr=curr->next;
      }
      return dummy->next;
    }
</pre>
