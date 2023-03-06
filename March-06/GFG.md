## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/07e45fe40846bc670ad2507d2c649304699768b9/1"> Geek hates too many 1s </a>]


#### ⭐<ins>Solution Function Code</ins> -


    int noConseBits(int n) {
        for(int i = 30; i>=2; i--){
            int mask1 = 1<<i;
            int mask2 = 1<<(i-1);
            int mask3 = 1<<(i-2);
            
            if((mask1&n) && (mask2&n) && (mask3&n)){
                n = (n^mask3);
            }
        }
        return n;
    }

