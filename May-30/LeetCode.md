## Problem of the Day - [<a href="https://leetcode.com/problems/design-hashset/"> 705. Design HashSet </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  vector<int> s;    
    MyHashSet() {        
        s.resize(1e6+1,0);
    }
    
    void add(int key) {        
        s[key] = 1;
    }
    
    void remove(int key) {
        s[key] = 0;
    }
    
    bool contains(int key) {
        return s[key];
    }
</pre>
#### ⭐<ins>Solution Function Code #2</ins> -
<pre>

  vector<bool> mp;    
    MyHashSet() {
        mp.resize(1000001, false);
    }

    void add(int key) {
        mp[key] = true;
    }

    void remove(int key) {
        mp[key] = false;
    }

    bool contains(int key) {
        return mp[key];
    }
</pre>
