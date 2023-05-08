## Problem of the Day - [<a href="https://leetcode.com/problems/merge-strings-alternately/"> 1768. Merge Strings Alternately </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     string mergeAlternately(string w1, string w2) {
          int j=0;
          string s = "";
          while(j < w1.length() || j < w2.length()){
              if(j<w1.length()) s += w1[j];
              if(j<w2.length()) s += w2[j];
              j++;
          }
          return s;
      }

