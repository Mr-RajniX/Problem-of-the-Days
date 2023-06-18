## Problem of the Day - [<a href="https://leetcode.com/problems/simplify-path/description/"> 71. Simplify Path </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


    string simplifyPath(string path) {
        stack<string> st;
        string res;        
        for(int i = 0;  i<path.size(); ++i){
            if(path[i] == '/')    
                continue;
            string temp;
            while(i < path.size() && path[i] != '/'){
                temp += path[i];
                ++i;
            }
            if(temp == ".")
                continue;
            else if(temp == ".."){
                if(!st.empty())
                    st.pop();
            }
            else
                st.push(temp);
        }
        while(!st.empty()){
            res = "/" + st.top() + res;
            st.pop();
        }
        if(res.size() == 0)
            return "/";
        
        return res;
    }

