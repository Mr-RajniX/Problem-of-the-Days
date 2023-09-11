### Problem of the Day : [1282. Group the People Given the Group Size They Belong To](https://leetcode.com/problems/group-the-people-given-the-group-size-they-belong-to/)

#### Solution :
<pre>
  vector< vector< int >> groupThePeople(vector<int>& groupSizes) {
        vector< vector< int >> people;
        map< int, vector< int >> group;
        for(int i=0; i < groupSizes.size(); i++){
            int desire = groupSizes[i];
            group[desire].push_back(i);
            if(group[desire].size() == desire){
                people.emplace_back(group[desire]);
                group[desire].clear();
            }
        }return people;
    }
</pre>
