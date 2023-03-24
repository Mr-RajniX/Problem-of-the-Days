## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/1e2f365be6114b671b915e145ec7dbcfdc432910/1"> Remove and Reverse </a>]


#### ⭐<ins>Solution Function Code</ins> -

    string removeReverse(string S) {
        int n=S.size();
        map<char,int> m;
        int mx=0;
        for(int i=0;i<n;i++){
            m[S[i]]++;
            mx=max(mx,m[S[i]]);
        }
        int i=0,j=n-1;
        bool front=true,back=true;
        int count=0;
        while(i<=j){
            if(front){
                if(m[S[i]]==1){
                    i++;
                }
                else{
                    m[S[i]]--;
                    S.erase(i,1);
                    j--;
                    count++;
                    back=true;
                    front=false;
                }
            }
            else if(back){
                if(m[S[j]]==1){
                    j--;
                }
                else{
                    m[S[j]]--;
                    S.erase(j,1);
                    j--;
                    count++;
                    front=true;
                    back=false;
                }
            }
        }
        if(count%2==1){
            reverse(S.begin(),S.end());
        }
        return S;
    }
