## Problem of the Day - [<a href="https://leetcode.com/problems/can-place-flowers/description/"> 605. Can Place Flowers </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    bool canPlaceFlowers(vector<int>& flowerbed, int n) {
        int i = 0;
        while (i < flowerbed.size() && n!=0) {
            if (flowerbed[i]==1){
                i+=2;
                continue;
            }
            if (((i==0&&flowerbed[0]==0)||flowerbed[i-1]==0)&&((i==flowerbed.size()-1&&flowerbed[i]==0)||flowerbed[i+1]==0)){
                n--;
                i+=1;
            }
            i++;

        }
        return n==0;
    }
</pre>
