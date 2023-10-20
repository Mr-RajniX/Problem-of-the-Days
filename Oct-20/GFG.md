#### Problem of the Day : [Form a number divisible by 3 using array digits](https://practice.geeksforgeeks.org/problems/form-a-number-divisible-by-3-using-array-digits0717/1)

#### Solution :
<pre>
  int isPossible(int N, int arr[]) {
        long long int sum  = 0;
        for(int i=0; i < N; i++) sum += arr[i];
        if(sum % 3 == 0) return 1;
        return 0;
    }
</pre>
