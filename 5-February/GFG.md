## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/eae1fbd0ac8f213a833d231e26ba4d829e79dd9c/1"> Intersection Point in Y Shaped Linked Lists </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int intersectPoint(Node* head1, Node* head2)
    {
        // Your Code Here
        Node* temp;
        temp = head1;
        while(temp != NULL){
            if(temp -> data < 0){
                temp -> data = (temp -> data - 1001);
            }else{
                temp -> data = (temp -> data + 1001);
            }
            temp = temp -> next;
        }
        Node* temp2;
        temp2 = head2;
        while(temp2 != NULL){
            if(temp2 -> data > 1000){
                return (temp2 -> data - 1001);
            }
            if(temp2 -> data < -1001){
                return (temp2 -> data + 1001);
            }
            temp2 = temp2 -> next;
        }
        return -1;
    }
</pre>
