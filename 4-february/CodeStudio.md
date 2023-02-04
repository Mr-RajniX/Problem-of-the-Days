## Problem of the Day - [<a href="https://www.codingninjas.com/codestudio/problems/periodic-string_1094904">Code Studio</a>]


#### ⭐<ins>Solution Codes</ins> -
<pre>
  ⭐Level : EASY - <a href="https://www.codingninjas.com/codestudio/problems/periodic-string_1094904">Periodic String</a>
    bool isPeriodic(string s) {
          // Write your code here.
          string t = s+s;
          if(t.substr(1,t.size()-2).find(s)!=-1){
              return true;
          }
          return false;
    }
</pre>
