```
class Solution {
    public int minMoves(int[] nums) {

        int min = Integer.MAX_VALUE;
        int totalMoves = 0;

        for (int num : nums) {
            if (num < min) min = num;
        }

        for (int i = 0; i < nums.length; i++) {
            int moves = (min >= nums[i] ? min - nums[i] : nums[i] - min);

            totalMoves += moves;

        }

        return totalMoves;

    }
}
```