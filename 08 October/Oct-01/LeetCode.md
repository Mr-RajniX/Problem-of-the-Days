### Problem of the Day : [557. Reverse Words in a String III](https://leetcode.com/problems/reverse-words-in-a-string-iii/)

##### Solution :
<pre>
  string reverseWords(string s) {
        istringstream stream(s);
        string word, ans;
        
        while (stream >> word) {
            reverse(word.begin(), word.end());
            ans += word + " ";
        }        
        if (!ans.empty()) {
            ans.pop_back();  
        }        
        return ans;
    }
</pre>
