#### Problem of the Day : [341. Flatten Nested List Iterator](https://leetcode.com/problems/flatten-nested-list-iterator/)

#### Solution :
<pre>
  vector< NestedInteger> nestedList;
    vector< int> flattenedList;
    int currentIndex = 0;
    void flatten(vector<NestedInteger>& currentList) {
        for (int i = 0; i < currentList.size(); i++) {
            if (currentList[i].isInteger()) {
                flattenedList.push_back(currentList[i].getInteger());
            } else {
                flatten(currentList[i].getList());
            }
        }
    }
public:
    NestedIterator(vector< NestedInteger> &nestedList) {
        this->nestedList = nestedList;
        flatten(nestedList);
    }
    
    int next() {
        int number = flattenedList[currentIndex];
        currentIndex++;
        return number;
    }
    
    bool hasNext() {
        return currentIndex < flattenedList.size();
    }
</pre>
