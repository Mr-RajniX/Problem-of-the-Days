## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/trace-path3840/1"> Trace Path </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     int isPossible(int n, int m, string s){
      int a=0,b=0,c=0,d=0;
      for(int i=0;i<s.length();i++) {
          if(s[i]=='L') { a++; if(b!=0) b--;}
          else if(s[i]=='R') { b++; if(a!=0) a--;}
          else if(s[i]=='D') { c++; if(d!=0) d--;}
          else if(s[i]=='U') { d++; if(c!=0) c--;}
          if(a>=m or b>=m or c>=n or d>=n) return 0;
       }
       return 1;
      }

