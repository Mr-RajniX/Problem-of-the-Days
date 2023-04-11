## Problem of the Day - [<a href="https://leetcode.com/problems/removing-stars-from-a-string/description/"> 2390. Removing Stars From a String </a>]


#### ⭐<ins>Solution Function Code #1</ins> [2 pointers approach] -

    string removeStars(string s) {
        int i=0,j=0;
        for(i=0;i<s.size();i++){
            if(s[i]=='*'){
                j--;
            }else{
                s[j++] = s[i];
            }
        }
        return s.substr(0,j);
    }

#### ⭐<ins>Solution Function Code #2</ins> [using stack] -

    string removeStars(string s) {
        stack<char> st;
        for (char c : s) {
            if (c == '*' && !st.empty()) {
                st.pop();
            } else {
                st.push(c);
            }
        }
        string ans;
        while (!st.empty()) {
            ans += st.top();
            st.pop();
        }
        reverse(ans.begin(), ans.end());
        return ans;
    }

