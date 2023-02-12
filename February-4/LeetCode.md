## Problem of the Day - [<a href="https://leetcode.com/problems/permutation-in-string/"> 567. Permutation in String </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

     bool checkInclusion(string s1, string s2) {
        int n1 = s1.size(), n2 = s2.size();
        if (n1 > n2){
            return false;
        }
        vector<int> arr1(26, 0), arr2(26, 0);
        for (char ch : s1){
            arr1[ch - 'a']++;
        }
        for (int i = 0; i < n2; i++)
        {
            arr2[s2[i] - 'a']++;
            if (i >= n1){
                arr2[s2[i - n1] - 'a']--;
            }
            if (arr1 == arr2)
                return true;
        }
        return false;
    }
</pre>
