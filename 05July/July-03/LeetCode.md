## Problem of the day : <a href="https://leetcode.com/problems/buddy-strings/"> 859. Buddy Strings </a>

### Solution :
<pre>
   bool buddyStrings(string s, string goal) {
        int n = s.length();
        if(s == goal){
            set< char > rev(s.begin(), s.end());
            return rev.size() < goal.size(); // Swapping same characters
        }

        int i = 0;
        int j = n - 1;

        while(i < j && s[i] == goal[i]){
            i++;
        }

        while(j >= 0 && s[j] == goal[j]){
            j--;
        }

        if(i < j){
            swap(s[i], s[j]);
        }

        return s == goal;
    }
</pre>
