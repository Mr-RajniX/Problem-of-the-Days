## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/6bb49b563cc171335c6564b00307a6d867e0268d/1"> Seating Arrangement </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     bool is_possible_to_get_seats(int n, int m, vector<int>& seats){
          int count=0;
          for(int i=0;i<m;i++){
             if(!seats[i]) {
               if((i-1<0||seats[i-1]==0) && (i+1>=m||seats[i+1]==0) ) {
                 count++;
                 seats[i]=1;
               }
              }  
          }
          return count>=n;
      }

