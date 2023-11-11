#### Problem of the Day : [Isomorphic Strings](https://www.geeksforgeeks.org/problems/isomorphic-strings-1587115620/1)

#### Solution :
<pre>
  bool areIsomorphic(string str1, string str2){
        int n=str1.size();
        if(str1.size()!=str2.size())
        return false;
        
        int map1[256]={0};
        int map2[256]={0};
        for(int i=0;i < str1.size();i++){
            if(map1[str1[i]-'a']!=map2[str2[i]-'a'])
                return false;
            map1[str1[i]-'a']=i+1;
            map2[str2[i]-'a']=i+1;
        }
        return true;
    }
</pre>
