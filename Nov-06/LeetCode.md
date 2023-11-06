#### Problem of the Day : [1845. Seat Reservation Manager](https://leetcode.com/problems/seat-reservation-manager/)

#### Solution [TLE]:
<pre>
    vector< bool> seats;
    int nextAvailableSeat;
    SeatManager(int n) {
        seats.assign(n, false); 
        nextAvailableSeat = 0;
    }
    
    int reserve() {
        while (nextAvailableSeat < seats.size() && seats[nextAvailableSeat]) {
            nextAvailableSeat++; 
        }
        if (nextAvailableSeat < seats.size()) {
            seats[nextAvailableSeat] = true; 
            return nextAvailableSeat + 1; 
        }
        return -1;
    }
    
    void unreserve(int seatNumber) {
        if (seatNumber > 0 && seatNumber <= seats.size()) {
            int seatIndex = seatNumber - 1;
            if (seats[seatIndex]) {
                seats[seatIndex] = false; 
                if (seatIndex < nextAvailableSeat) {
                    nextAvailableSeat = seatIndex; 
                }
            }
        }
    }
</pre>

#### Solution :
<pre>
    priority_queue< int, vector< int>, greater< int>> seats;
    int nextAvailableSeat;
    SeatManager(int n) {
        for (int i = 1; i <= n; i++) {
            seats.push(i);
        }
    }
    
    int reserve() {
        if (!seats.empty()) { 
            int reservedSeat = seats.top(); 
            seats.pop();
            return reservedSeat; 
        } else {
            return -1; 
        }
    }
    
    void unreserve(int seatNumber) {
        seats.push(seatNumber);
    }
</pre>
