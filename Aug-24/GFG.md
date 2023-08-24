### Problem of the Day : [Multiply two strings](https://practice.geeksforgeeks.org/problems/multiply-two-strings/1)

#### Solution :
<pre>
  string multiplyStrings(string s1, string s2) {
       //Your code here
        bool negative=false;
       if(s1[0]=='-' && s2[0]=='-'){
           s1=s1.substr(1);
           s2=s2.substr(1);
       }
       else if(s1[0]=='-'){
           s1=s1.substr(1);
           negative=true;
       }
       else if(s2[0]=='-'){
           negative=true;
           s2=s2.substr(1);
       }
       int m=s2.length();
       int n=s1.length();
       
       string ans="";
       for(int j=m-1;j >= 0;j--){
           int val1=s2[j]-'0';
           int carry=0;

           for(int i=n-1,k=m-j-1;i >= 0;i--,k++){
               int sum=((s1[i]-'0')*val1)+carry;
               
               carry=sum/10;
               if(ans[k]!='\0'){
                   int val1=((sum%10))+(ans[k]-'0');
                   carry+=(val1/10);
                   
                   ans[k]=(val1%10+'0');
               }
               else{
                   ans.push_back(sum%10+'0');
               }
           }
           if(carry) ans.push_back(carry+'0');
       }
       reverse(ans.begin(),ans.end());
       
       int size=ans.length();
       int i=0;
       while(i < size-1){
           if(ans[i]!='0'){
               break;
           }
           i++;
       }
       ans=ans.substr(i);
       if(size==1 && ans[0]=='0') return "0";
       
       if(negative) return "-"+ans;
       return ans;
    }
</pre>
