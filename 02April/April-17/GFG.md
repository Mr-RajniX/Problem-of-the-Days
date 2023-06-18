## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/00ae30d0e0f6d8877c68f8b8558c5b0138fdb4b7/1"> Job Sequencing Problem </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


    vector<int> JobScheduling(Job a[], int n) { 
        sort(a,a+n,[](Job &x,Job &y){ return x.profit>y.profit; });
        
        int maxa=-1;
        int count = 0;
        int sum = 0;
        for(int i =0;i<n;i++){
            maxa=max(maxa,a[i].dead);
        }
        vector<int>v(maxa+1,-1);
        for(int i =0;i<n;i++){
            for(int j = a[i].dead;j>0;j--){
                if(v[j]==-1){
                    v[j]=1;
                    count++;
                    sum+=a[i].profit;
                    break;
                }
            }
        }
        return {count,sum};
    } 

