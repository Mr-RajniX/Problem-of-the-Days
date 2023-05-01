## Problem of the Day - [<a href="https://leetcode.com/problems/average-salary-excluding-the-minimum-and-maximum-salary/"> 1491. Average Salary Excluding the Minimum and Maximum Salary </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     double average(vector<int>& salary) {
          sort(salary.begin(),salary.end());
          int sum=0;
          double avg;
          for(int i=1;i<salary.size()-1;i++){
              sum+=salary[i];
          }
          avg=(double)sum/(salary.size()-2);
          return avg;
      }

