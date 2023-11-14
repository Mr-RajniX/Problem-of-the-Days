#### Problem of the Day : [Check if strings are rotations of each other or not](https://www.geeksforgeeks.org/problems/check-if-strings-are-rotations-of-each-other-or-not-1587115620/1)

#### Solution :
<pre>
  bool areRotations(string s1,string s2){
        s1+=s1;
        return s1.find(s2)!=string::npos;
    }
</pre>
