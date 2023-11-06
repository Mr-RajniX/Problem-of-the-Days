#### Problem of the Day : [1845. Seat Reservation Manager](https://leetcode.com/problems/seat-reservation-manager/)

#### Solution :
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
