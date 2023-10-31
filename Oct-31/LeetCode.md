#### Problem of the Day : [2433. Find The Original Array of Prefix Xor](https://leetcode.com/problems/find-the-original-array-of-prefix-xor/)

#### Solution :
<pre>
  vector< int> findArray(vector< int>& pref) {
        vector< int> v(pref.size());
        v[0] = pref[0];
        for(int i=1; i < pref.size(); i++){
            v[i] = pref[i] ^ pref[i-1];            
        }return v;
    }
</pre>
