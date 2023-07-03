## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/reversing-the-equation2205/1"> Reversing the equation </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  string reverseEqn (string s){
      string n="",f="";
      for(int i=s.size()-1;i >= 0;i--){
          if(s[i] >= 48&&s[i] <= 57){
              string f="";
              f+=s[i];
              n.insert(0,f);
          }
          else{
              f+=n;
              f+=s[i];
              n="";
          }
      }
      f+=n;
      return f;
  }
</pre>
