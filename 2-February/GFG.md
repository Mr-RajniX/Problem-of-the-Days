## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/2e068e2342b9c9f40cfda1ed8e8119542d748fd8/1"> Last cell in a Matrix </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>
     pair<int,int> endPoints(vector<vector<int>> matrix, int R, int C){
        int i=0,j=0;
        int n=matrix.size(),m=matrix[0].size();
        int dirn=0;
        int first,second;
        while(i>=0 && j>=0 && i<n && j<m)
        {
            if(matrix[i][j]==1)
            {
                dirn=(dirn+1)%4;
                matrix[i][j]=0;
            }
            first=i,second=j;
            if(dirn==0)
                j++;
            else if(dirn==1)
                i++;
            else if(dirn==2)
                j--;
            else
                i--;
        }
        return {first,second};
      }
  };
</pre>
