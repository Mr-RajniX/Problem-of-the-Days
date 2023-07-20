### Problem of the Day : [Non Repeating Character](https://practice.geeksforgeeks.org/problems/non-repeating-character-1587115620/1)

#### Solution :
<pre>
  char nonrepeatingCharacter(string S)
    {
       map< char, int > mp;
       for(auto x : S) mp[x]++;
       
       for(auto x : S)
           if(mp[x] == 1) 
           return x;
       
       return '$';
    }
</pre>
