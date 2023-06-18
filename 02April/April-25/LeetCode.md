## Problem of the Day - [<a href="https://leetcode.com/problems/smallest-number-in-infinite-set/"> 2336. Smallest Number in Infinite Set </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   unordered_set<int> isPresent;
    priority_queue<int, vector<int>, greater<int>> addedIntegers;
    int currentInteger;

public:
    SmallestInfiniteSet() {
        currentInteger = 1;
    }

    int popSmallest() {
        int answer;
        if (!addedIntegers.empty()) {
            answer = addedIntegers.top();
            isPresent.erase(answer);
            addedIntegers.pop();
        } 
        else {
            answer = currentInteger;
            currentInteger += 1;
        }
        return answer;
    }

    void addBack(int num) {
        if (currentInteger <= num || 
            isPresent.find(num) != isPresent.end()) {
            return;
        }
        addedIntegers.push(num);
        isPresent.insert(num);
    }
</pre>
