#### Problem of the Day : [Check if string is rotated by two places](https://www.geeksforgeeks.org/problems/check-if-string-is-rotated-by-two-places-1587115620/1)

#### Solution :
<pre>
  bool isRotated(string str1, string str2){
        reverse(str1.begin(),str1.end());
        reverse(str1.begin(),str1.begin()+2);
        reverse(str1.begin()+2,str1.end());        
        if(str1 == str2)     
            return true;
        reverse(str1.begin(),str1.begin()+4);
        reverse(str1.begin()+4,str1.end());
        reverse(str1.begin(),str1.end());
        return str1 == str2;    
        
    }
</pre>
