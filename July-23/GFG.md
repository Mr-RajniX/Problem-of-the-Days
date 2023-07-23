### Problem of the Day : [Given a linked list of 0s, 1s and 2s, sort it](https://practice.geeksforgeeks.org/problems/given-a-linked-list-of-0s-1s-and-2s-sort-it/1)

#### Solution :
<pre>
  Node* segregate(Node *head) {
        int arr[3]={0};
        Node* temp =head;
        int ll;
        while(temp){
            arr[temp->data]+=1;
            temp=temp->next;
        }
        temp=head;
        while(temp){
            if(arr[0]!=0){
                temp->data=0;
                arr[0]--;
                temp=temp->next;
            }
           else if(arr[1]!=0){
                temp->data=1;
                arr[1]--;
                temp=temp->next;
            }
            else{
                temp->data=2;
                arr[2]--;
                temp=temp->next;
            }
        }
        return head;
    }
</pre>
