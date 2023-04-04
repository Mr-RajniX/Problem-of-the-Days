## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/6a1b365b520f10c8a29b533eb72951b4b4237b57/1"> Minimum Steps Required </a>]


#### ⭐<ins>Solution Function Code</ins> -


        int minSteps(string str){
            int cnt=0, cnt1=0;
            for(int i=1;i<str.size();i++){
                if(str[i-1]=='a' && str[i]=='b')
                cnt++;
                else if(str[i-1]=='b' && str[i]=='a')
                cnt1++;
            }
            return max(cnt+1, cnt1+1);
        }
