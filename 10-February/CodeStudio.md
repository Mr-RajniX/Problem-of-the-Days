## Problem of the Day - [<a href="https://www.codingninjas.com/codestudio/problems/check-if-one-string-is-a-rotation-of-another-string_1115683">Code Studio</a>]


#### ⭐<ins>Solution Codes</ins> -
<pre>
  ⭐Level : EASY - <a href="https://www.codingninjas.com/codestudio/problems/check-if-one-string-is-a-rotation-of-another-string_1115683">Check If One String Is A Rotation Of Another String</a>
    int isCyclicRotation(string &p, string &q) 
    {
        if(p.size()!=q.size())
            return 0;

        string s=p+p;
        if(s.find(q)!=string::npos)
            return 1;
        else
            return 0;
    }
</pre>
