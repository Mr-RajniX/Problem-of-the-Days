## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/hands-of-straights/1"> Hands of Straights </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>
bool isStraightHand(int N, int groupSize, vector<int> &hand) {
    if(N % groupSize) return false;        
    map<int, int> m;
    for(int i : hand) m[i]++;        
    int k = N / groupSize;
    while(k--) {
        int pre = m.begin() -> first;
        m[pre]--;
        if(!m[pre]) m.erase(pre);            
        for(int i=1; i < groupSize; i++) {
            if(m.find(pre + 1) == m.end()) return false;
            pre += 1;
            m[pre]--;
            if(!m[pre]) m.erase(pre);
        }
    }
    return true;        
}
