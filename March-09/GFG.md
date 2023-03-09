## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/de6f6a196aecdfb3e4939ba7729809a5a4bdfe90/1"> Find anagrams in linked list </a>]


#### ⭐<ins>Solution Function Code</ins> -


    vector<Node*> findAnagrams(struct Node* head, string s){
        vector<Node*> res;
        vector<int> v(26);
        for(int i=0; i<s.size(); i++)
            v[s[i]-'a']+=1;
        int n=s.size();
        Node* a=head;
        Node* b=head;
        Node* d=head;
        while(b!=NULL){
            vector<int> t(26);
            int i=0;
            while(i<n && b!=NULL){
                char c=b->data;
                t[c-'a']+=1;
                i+=1;
                d=b;
                b=b->next;
            }
            while(v!=t && b!=NULL){
                t[a->data-'a']-=1;
                a=a->next;
                d=b;
                t[b->data-'a']+=1;
                b=b->next;
            }
            if(v==t){
                d->next=NULL;
                res.push_back(a);
                a=b;
            }
        }
        return res;
    }
