## Problem of the Day - [<a href="https://www.codingninjas.com/codestudio/problems/specific-order_1102295?leftPanelTab=0">Code Studio</a>]


#### ⭐<ins>Solution Codes</ins> -
<pre>
  ⭐Level : EASY - <a href="https://www.codingninjas.com/codestudio/problems/specific-order_1102295?leftPanelTab=0">Custom Sort String</a>
    string specificOrder(string & s, string & order) {
        int a[26] = {0};
        for (auto i : s){
            a[i-'a']++;
        }
        string str = "";
        for (auto i : order){
            if (a[i-'a'] > 0){
                str.insert(str.end(),a[i-'a'], i);
                a[i-'a'] = 0;
            }
        }
        for (auto i : s){
            if (a[i-'a'] > 0){
                str.push_back(i);
            }
        }
        return str;
    }
</pre>
