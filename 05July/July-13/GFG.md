### Problem of the Day : [Unique Number of Occurrences](https://practice.geeksforgeeks.org/problems/unique-frequencies-of-not/1)

#### Solution :
<pre>
  bool isFrequencyUnique(int n, int arr[])
    {
        unordered_map< int,int > mp;
        for(int i = 0; i < n; i++) mp[arr[i]]++;
        
        unordered_set< int > Freq;
        
        for(auto i = mp.begin(); i != mp.end(); i++){
            if(Freq.count(i -> second) > 0) return false;
            Freq.insert(i -> second);
        }
        
        return true;
    }
</pre>
