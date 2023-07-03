## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/arranging-the-array1131/1"> Arranging the array </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  void Rearrange(int arr[], int n){
            vector<int>v1;
            vector<int>v2;
            for(int i=0;i < n;i++){
                if(arr[i]<0){
                   v1.push_back(arr[i]);
                }
                else{
                    v2.push_back(arr[i]);
                } 
            }
            v1.insert(v1.end(),v2.begin(),v2.end()); 
            for(int i=0;i < n;i++){
                arr[i]=v1[i];
            }
        }
</pre>
