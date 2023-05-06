## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/09b910559335521654aa2909f86f893447d8f5ba/1"> Another Coin Change Problem </a>]


#### ⭐<ins>Solution Function Code #1</ins> -

     bool makeChanges(int n, int k, int t, vector<int> &c) {
          // code here
          int a[k+1][t+1];
          int y;
          a[0][0]=1;
          for(int i=0;i<=k;++i)
          {
              for(int j=0;j<=t;++j)
              {
                  if(i==0&&j==0)continue;
                  if(i*c[0]==j)a[i][j]=1;
                  else a[i][j]=0;
              }
          }
          y=a[k][t];
          if(y==1)return true;
          int temp,t1,t2;
          for(int p=1;p<c.size();++p)
          {
              for(int i=1;i<=k;++i)
              {
                  for(int j=1;j<=t;++j)
                  {
                      temp=0;
                      temp+=a[i][j];
                      t1=i-1;
                      t2=j-c[p];
                      if(t1==0&&t2==0)
                      {
                          a[i][j]=1;
                          continue;
                      }
                      if(t1>0&&t2>0)temp+=a[t1][t2];
                      if(temp>0)a[i][j]=1;
                      else a[i][j]=0;
                  }
              }
              y=a[k][t];
              if(y==1)return true;
          }
          return false;
      }

