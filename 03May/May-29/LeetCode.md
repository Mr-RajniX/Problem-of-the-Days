## Problem of the Day - [<a href="https://leetcode.com/problems/design-parking-system/"> 1603. Design Parking System </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    int big;
    int medium;
    int small;

    ParkingSystem(int big, int medium, int small) {
        this->big = big;
        this->medium = medium;
        this->small = small;
    }
    
    bool addCar(int carType) {        
        if(carType == 1 && big == 0 || carType == 2 && medium == 0 || carType == 3 && small == 0)
          return false;

        if(carType == 1) big--;
        if(carType == 2) medium--;
        if(carType == 3) small--;

        return true;
    }
</pre>
