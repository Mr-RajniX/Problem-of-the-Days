### Problem of the Day : [Reverse a String](https://practice.geeksforgeeks.org/problems/reverse-a-string/1)

#### Solution :
<pre>
  string reverseWord(string str){
        int s = 0, e = str.length()-1;
        while(s <= e){
            swap(str[s],str[e]);
            s++;e--;
        }
        return str;
    }
</pre>
