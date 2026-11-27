```
class Solution {
    public int elevatorRequests(int n, int[] requests) {

        int time = requests[0];

        for (int f = 1; f < requests.length; f++) {
            time = time + Math.abs(requests[f] - requests[f-1]);
        }

        return time;
    }
}
```
