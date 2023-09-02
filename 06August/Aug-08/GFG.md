### Problem of the day : [Fraction pairs with sum 1](https://practice.geeksforgeeks.org/problems/fraction-pairs-with-sum-1/1)

#### Solution :
<pre>
  int countFractions(int n, int numerator[], int denominator[]){
        int sum = 0;
        map< float,int > mp;
        for(int i=0;i < n;i++){
            float x = ((float)(denominator[i]-numerator[i]))/(float)denominator[i];
            if(mp.find(x)!=mp.end()){
                sum+=mp[x];
            }
            float t = ((float)numerator[i])/((float)(denominator[i]));
            mp[t]++;
        }
        return sum;
    }
</pre>
