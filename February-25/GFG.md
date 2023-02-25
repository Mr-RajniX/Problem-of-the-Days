## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/13eb74f1c80bc67d526a69b8276f6cad1b8c3401/1"> Valid Compressed String </a>]


#### ⭐<ins>Solution Function Code</ins> -


    int checkCompressed(string S, string T) {
        // code here
        int i=0,j=0;
        while(i<S.length() && j<T.length()){
            if(S[i]==T[j]){
                i++;
                j++;
                continue;
            }
            if(T[j]-'0'==0){
                j++;
                continue;
            }
            
            int count=0;
            while(j<T.length() && isdigit(T[j])){
                count=count*10 + (T[j]-'0');
                j++;
            }
            
            i+=count;
            if(count==0) return 0;
        }
        return i==S.length() && j==T.length();
    }
