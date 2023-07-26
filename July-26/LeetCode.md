### Problem of the Day : [1870. Minimum Speed to Arrive on Time](https://leetcode.com/problems/minimum-speed-to-arrive-on-time/)

#### Solution :
<pre>
  int minSpeedOnTime(vector< int >& dist, double hour) {
        int n = dist.size(); 
        int minSpeed = 1, maxSpeed = 1e7 + 1;
        int answer = -1; 
        while (minSpeed < maxSpeed) { 
            int midSpeed = minSpeed + (maxSpeed - minSpeed) / 2;

            double totalHours = 0.0; 
            for (int i = 0; i < n - 1; ++i) {
                totalHours += std::ceil(static_cast< double >(dist[i]) / midSpeed);
            }
            totalHours += static_cast< double >(dist[n - 1]) / midSpeed;
            if (totalHours > hour) {
                minSpeed = midSpeed + 1;
            } else {
                answer = midSpeed;
                maxSpeed = midSpeed;
            }
        }
        return answer;
    }
</pre>
