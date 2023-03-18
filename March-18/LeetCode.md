## Problem of the Day - [<a href="https://leetcode.com/problems/design-browser-history/description/"> 1472. Design Browser History </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int ele;
    vector<string> vc;
    BrowserHistory(string homepage) {
        vc.push_back(homepage);
        ele  =0;
    }
    
    void visit(string url) {
        int l = vc.size()-1;
        while(l>ele){
            vc.pop_back();
            l--;
        }
        ele++;
        vc.push_back(url);
    }
    
    string back(int steps) {
        ele-=steps;
        if(ele<0) ele=0;
        return vc[ele];
    }
    
    string forward(int steps) {
        ele +=steps;
        if(ele>=vc.size()) ele = vc.size()-1;
        return vc[ele];
    }
</pre>
