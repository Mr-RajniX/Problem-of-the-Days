#### Problem of the Day : [Sum of XOR of all pairs](https://practice.geeksforgeeks.org/problems/sum-of-xor-of-all-pairs0723/1)

#### Solution :
<pre>
  long long int sumXOR(int arr[], int n){
    	long long int ans = 0;
        for(int i=0; i < 32; i++){
            long long int one=0, zero = 0;
            for(int j=0; j < n; j++){
                if( arr[j] & 1) one++;
                else zero++;
                arr[j] /= 2;
            }
            ans += one*zero*pow(2,i);
        }
        return ans; 
    }
</pre>
