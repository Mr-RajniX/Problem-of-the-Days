#### Problem of the Day : [1441. Build an Array With Stack Operations](https://leetcode.com/problems/build-an-array-with-stack-operations/description/)

#### Solution :
<pre>
  vector< string> buildArray(vector< int>& target, int n) {
        vector< string> operations;
        int targetIndex = 0;        
        for (int i = 1; i <= n; i++) {
            if (targetIndex == target.size()) {
                break;  
            }
            if (target[targetIndex] == i) {
                operations.push_back("Push");
                targetIndex++;
            } else {
                operations.push_back("Push");
                operations.push_back("Pop");
            }
        }
        return operations;
    }
</pre>
