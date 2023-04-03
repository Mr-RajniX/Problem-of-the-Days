## Problem of the Day - [<a href="https://www.codingninjas.com/codestudio/problem-details/valid-word-abbreviations_1171044">Code Studio</a>]


#### ⭐<ins>Solution Codes</ins> -
<pre>
  ⭐Level : EASY - <a href="https://www.codingninjas.com/codestudio/problem-details/valid-word-abbreviations_1171044">Valid Word Abbreviations</a>
    bool validAbbreviation (string &word, string &abbr) {
        // Write your code here.
        int i = 0;  // word's index
          int j = 0;  // abbr's index

          while (i < word.length() && j < abbr.length()) {
            if (word[i] == abbr[j]) {
              ++i;
              ++j;
              continue;
            }
            if (abbr[j] <= '0' || abbr[j] > '9')
              return false;
            int num = 0;
            while (j < abbr.length() && isdigit(abbr[j])) {
              num = num * 10 + abbr[j] - '0';
              ++j;
            }
            i += num;
          }

          return i == word.length() && j == abbr.length();
      }
</pre>



