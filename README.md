# Seat-Reservation-Manager
 Implement the SeatManager class:  SeatManager(int n) Initializes a SeatManager object that will manage n seats numbered from 1 to n. All seats are initially available. int reserve() Fetches the smallest-numbered unreserved seat, reserves it, and returns its number. void unreserve(int seatNumber) Unreserves the seat with the given seatNumber.

class SeatManager:
    def __init__(self, n: int):
        self.hq = []
        self.current = 0

    def reserve(self) -> int:
        if self.hq:
            return heapq.heappop(self.hq)
        self.current += 1
        return self.current

    def unreserve(self, seatNumber: int) -> None:
        heapq.heappush(self.hq, seatNumber)
