## Problem of the Day - [<a href="https://leetcode.com/problems/greatest-common-divisor-of-strings/description/"> 1071. Greatest Common Divisor of Strings </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    string gcdOfStrings(string str1, string str2) {
        // return (str1 + str2 == str2 + str1)? str1.substr(0, gcd(size(str1),size(str2))): "";
        if(str1 + str2 == str2 + str1){
            return str1.substr(0, gcd(str1.length(), str2.length()));
        }
        return "";
    }
</pre>
