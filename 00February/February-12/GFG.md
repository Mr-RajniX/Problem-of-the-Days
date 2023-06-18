## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/6cb0782855c0f11445b8d70e220f888e6ea8e22a/1"> Prime List </a>]


#### ⭐<ins>Solution Function Code</ins> -


    bool isPrime(int n){
        if(n==1 or n<=0) return false;
        for(int i=2; i<=sqrt(n); i++){
            if(n%i==0){
                return false;
            }
        }
        return true;
    }
    Node *primeList(Node *head){
        Node* root=head;
        while(head!=NULL){
            int temp = head->val;
            
            if(isPrime(temp)){
                head = head->next;
                continue;
            }
            else{
                int temp2 = temp;
                while(!isPrime(temp) and !isPrime(temp2)){
                    temp++;
                    temp2--;
                }
                
                if(isPrime(temp) and isPrime(temp2)){
                    head->val = min(temp,temp2);
                }
                else if(isPrime(temp2)){
                    head->val = temp2;
                }
                else{
                    head->val = temp;
                }
                
                head = head->next;
            }
        }
        return root;
    }

