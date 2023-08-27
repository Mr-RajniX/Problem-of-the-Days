### Problem of the Day : [403. Frog Jump](https://leetcode.com/problems/frog-jump/)

#### Solution :
<pre>
  bool canCross(vector< int> & stones) {
        unordered_map< int, unordered_set< int >> mp;
        mp[stones[0]] = {0}; 
        for (int i = 0; i < stones.size(); ++i) {
            int position = stones[i];
            for (auto it : mp[position])
                for (int jump = it - 1; jump <= it + 1; ++jump) 
                    if (jump > 0)
                        mp[stones[i] +  jump].insert(jump);    

        }
        return !mp[stones.back()].empty();
    }
</pre>
