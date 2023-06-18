## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/express-as-sum-of-power-of-natural-numbers5647/1"> Express as sum of power of natural numbers </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


    int numOfWays(int n, int x){
          vector<int> coins , first(n+1,0) , second(n+1,0) ;
          first[0] = 1;
          for(int i=1;pow(i,x)<=n;i++) coins.push_back(pow(i,x));
          for(int i=0;i<coins.size();i++){
              for(int j=0;j<=n;j++){
                  second[j] = first[j];
                  if(j>=coins[i]) second[j] = ((long long)second[j] + first[j-coins[i]])%((long long)1e9+7);
              } first = second;
          }
          return second[n];
      }

