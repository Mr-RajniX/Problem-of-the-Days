## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/55dbfdc246f3f62d6a7bcee7664cacf6be345527/1"> Add Minimum Characters </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    int addMinChar(string str){    
        int st = 0;
        int end = str.size()-1;
        int ans = 0;
        while(st<=end){
            if(str[st]==str[end]){
                st++; end--;
            }else{
                ans++;
                st = 0;
                end = str.size()-1-ans;
            }
        }
        return ans;
    }
</pre>
