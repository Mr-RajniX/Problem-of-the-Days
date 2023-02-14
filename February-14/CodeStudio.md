## Problem of the Day - [<a href="https://www.codingninjas.com/codestudio/problems/check-if-two-given-strings-are-isomorphic-to-each-other_1117636" target="_blank">Code Studio</a>]


#### ⭐<ins>Solution Codes</ins> -

  ⭐Level : EASY - <a href="https://www.codingninjas.com/codestudio/problems/check-if-two-given-strings-are-isomorphic-to-each-other_1117636" target="_blank">Isomorphic Strings</a>
  
    #define MAX_CHARS 256
    bool areIsomorphic(string &str1, string &str2)
    {
        // Write your code here
        int m = str1.length();   int n = str2.length();
        if(m != n) return false;
        bool marked[MAX_CHARS] = { false };
        int map[MAX_CHARS];
        memset(map, -1, sizeof(map));
        for(int i=0; i<n; i++){
            if(map[str1[i]] == -1){
                if(marked[str2[i]] == true) return false;
                marked[str2[i]] = true;
                map[str1[i]] = str2[i];
            }
            else if(map[str1[i]] != str2[i]) return false;
        }
        return true;
    }



