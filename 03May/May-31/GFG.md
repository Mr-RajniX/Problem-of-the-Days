## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/frequency-game/1"> Frequency Game </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int LargButMinFreq(int arr[], int n) {
        unordered_map<int, int> mp;
        for(int i=0; i < n; i++) mp[arr[i]]++;
        int freq=INT_MAX;
        for(auto pr:mp) freq = min(freq, pr.second);
        int element=0;
        for(auto pr:mp) if (pr.second == freq) element = max(element, pr.first);
        return element;
    }
</pre>
