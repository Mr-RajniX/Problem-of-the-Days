## Problem of the Day - [<a href="https://leetcode.com/problems/successful-pairs-of-spells-and-potions/"> 2300. Successful Pairs of Spells and Potions </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int valid_pos(vector<int>& potions, long long success, int spell){
        long potion_needed = (success + spell - 1) / spell;

        int l=0,r=potions.size();
        while(l<r){
            int mid = l + (r-l)/2;
            if(potions[mid] >= potion_needed)
                r = mid;
            else
                l = mid + 1;
        }
        return l;
    }

    vector<int> successfulPairs(vector<int>& spells, vector<int>& potions, long long success) {
        sort(potions.begin(), potions.end());
        vector<int> res;
        for (int spell: spells) {
            res.push_back(potions.size()- valid_pos(potions, success, spell));
        }
        return res;
    }
</pre>
