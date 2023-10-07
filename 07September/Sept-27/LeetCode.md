### Problem of the Day : [880. Decoded String at Index](https://leetcode.com/problems/decoded-string-at-index/)

##### Solution :
<pre>
  string decodeAtIndex(string s, int k) {
        long long decodedLength = 0; 
        for (auto character : s) {
            if (isdigit(character)) 
                decodedLength *= character - '0';
            else 
                decodedLength++;
        }
        for (int i = s.size() - 1; i >= 0; i--) {
            if (isdigit(s[i])) {
                decodedLength /= (s[i] - '0');
                k = k % decodedLength;
            } else {
                if (k == 0 || decodedLength == k)
                    return string("") + s[i]; 
                decodedLength--;
            }
        }

        return ""; 
    }
</pre>
