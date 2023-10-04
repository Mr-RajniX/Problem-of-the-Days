### Problem of the Day : [Roman Number to Integer](https://practice.geeksforgeeks.org/problems/roman-number-to-integer3201/1)

#### Solution :
<pre>
  int romanToDecimal(string &str) {
        int n=str.length();
        if(n==1) return convert(str[0]);
        int count=0;
        for(int i=0;i < n-1;i++){
            if(convert(str[i]) >= convert(str[i+1])) 
                count+=convert(str[i]);
            else 
                count-=convert(str[i]);
        }
        count+=convert(str[n-1]);
        return count;
    }
    int convert(char c){
        int num=0;
        if(c=='I') num=1;
        else if(c=='V') num=5;
        else if(c=='X') num=10;
        else if(c=='L') num=50;
        else if(c=='C') num=100;
        else if(c=='D') num=500;
        else if(c=='M') num=1000;
        return num;
    }
</pre>
