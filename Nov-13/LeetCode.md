#### Problem of the Day : [2785. Sort Vowels in a String](https://leetcode.com/problems/sort-vowels-in-a-string/)

#### Solution :
<pre>
  string sortVowels(string s) {
        vector< char> vol;
        for( char c : s){
            if(string("aeiouAEIOU").find(c) != string::npos) vol.push_back(c);
        }
        sort(vol.begin(), vol.end(), greater< char>());

        string ans;
        for( char c : s){
            if(string("aeiouAEIOU").find(c) != string::npos){
                ans += vol.back();
                vol.pop_back();
            } else ans += c;
        } return ans;
    }
</pre>
