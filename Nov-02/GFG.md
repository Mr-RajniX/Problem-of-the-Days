#### Problem of the Day : [Minimum distance between two numbers](https://www.geeksforgeeks.org/problems/minimum-distance-between-two-numbers/1)

#### Solution :
<pre>
  int minDist(int arr[], int n, int x, int y) {
        int ind=-1,x_position=-1,y_position=-1,d=INT_MAX;
        for(int i=0;i < n;i++){
            if(arr[i]==x || arr[i]==y){
                if(arr[i]==x)x_position=i;
                else y_position=i;
            }
        }
        if(x_position==-1|| y_position==-1 )return -1;
        x_position=-1,y_position=-1;
        for(int i=0;i < n;i++){
            if(arr[i]==x){
                x_position=i;
                if(y_position!=-1)
                    d=min(d,abs(x_position - y_position));
            }
            if(arr[i]==y){
                y_position=i;
                if(x_position!=-1)
                    d=min(d, abs(x_position - y_position));
            }
        }
        return d;
    }
</pre>
