## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/d7cd0429f9cf85f421831c4f6d50fad99566c1f9/1"> Special Palindrome Substrings </a>]


#### ⭐<ins>Solution Function Code</ins> -


    int findopern(string& temp,int num1,int m)
    {
        int start=0,end=temp.length()-1;
        int opern=0;
        while(start<=end){
            if(temp[start]!=temp[end]){
                if(start>=num1 && end<=(num1+m-1)) return 1e9;
                opern++;
            }
            start++;
            end--;
        }
        return opern;
    }
    int specialPalindrome(string s1, string s2){
        int n=s1.length(),m=s2.length();
        string temp=s1;
        int mini=1e9;
        for(int i=0;i<=n-m;i++){
            int op=0; 
            for(int j=0;j<m;j++){
                if(temp[i+j]!=s2[j]) op++;
                
                temp[i+j]=s2[j];
            }
            mini=min(mini,op+findopern(temp,i,m));
            temp=s1;
        }
        if(mini==1e9) return -1;
        return mini;
    }
