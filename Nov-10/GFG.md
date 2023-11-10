#### Problem of the Day : [Number following a pattern](https://www.geeksforgeeks.org/problems/number-following-a-pattern3126/1)

#### Solution :
<pre>
  string printMinNumberForPattern(string S){
    bool dec=false;
    string ans="";
    int mini=0;
    int cnt=0;
    for(int i=0;i < S.size();i++){
        if(S[i]=='I'){
            if(!dec){ 
                mini++;
                ans.push_back(mini+'0');
            }else{
                dec=false;
                int oldmini=mini;
                mini+=cnt+1;cnt=0;
                for(int j=mini;j>oldmini;j--) ans.push_back(j+'0');
            }
        }else{
            dec=true;
            cnt++; 
        }
    }
    if(S[S.size()-1]){
        int oldmini=mini;
        mini+=cnt+1;
        for(int j=mini;j>oldmini;j--) ans.push_back(j+'0');    
    }
    return ans;
    }
</pre>
