## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/c928f229cc972671d91c5e9f6b222414912cc88a/1"> Easy Task </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


       private:
        void query1(int i , string &s , char ch)
        {
            s[i] = ch;
        }    
        char query2(int left , int right , int k  , string s)
        {
            vector<int> v(26);
            for(int i = left;i<=right; i++)
            {
                v[s[i]-'a']++;
            }
            int sum = 0;
            for(int i = 25; i>= 0; i--)
            {
                sum += v[i];
                if(sum >= k)
                {
                    return i + 'a';
                }
            }
            return 'z';
        }


    public:
        vector<char> easyTask(int n,string s,int q,vector<vector<string>> &queries){
           vector<char> ans;
           for(int i = 0; i<q; i++)
           {
               int q = queries[i][0][0] - '0';
               if(q == 1)
               {
                   query1(stoi(queries[i][1]) , s , queries[i][2][0]);
               }
               if(q == 2)
               {
                   char chh;
                   chh = query2(stoi(queries[i][1]) , stoi(queries[i][2]) , stoi(queries[i][3]), s );
                   ans.push_back(chh);
               }
           }
           return ans;
        }

