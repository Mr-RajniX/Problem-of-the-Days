## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/prefix-match-with-other-strings/1"> Prefix match with other strings </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int klengthpref(string arr[], int n, int k, string str){    
        int ans=0;
        if(k > str.size())return 0;
        string sbstr=str.substr(0,k);
        string sbstr_ofarr="";
        for(int i=0;i < n;i++){      
            sbstr_ofarr=arr[i].substr(0,k);
            if(sbstr==sbstr_ofarr){
                ans++;
            }
        }
        return ans;
    }
</pre>
