## Problem of the Day - [<a href="https://leetcode.com/problems/design-underground-system/"> 1396. Design Underground System </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    unordered_map<int,pair<string,int>>checkInStation; 
    unordered_map<string,pair<int,int>> checkOutStation;
    
    UndergroundSystem() {
    }
    
    void checkIn(int id, string stationName, int t) {
        checkInStation[id] = {stationName,t};
    }
    
    void checkOut(int id, string stationName, int t){         
        auto cIn = checkInStation[id];
        checkInStation.erase(id);
        string route = cIn.first + "_" + stationName;
        checkOutStation[route].first += t - cIn.second;
        checkOutStation[route].second += 1;  
    }
    
    double getAverageTime(string startStation, string endStation) {
        string route  = startStation + "_" + endStation;
        auto time = checkOutStation[route];
        return (double)time.first/time.second;
    }
</pre>
