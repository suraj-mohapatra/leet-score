```
class Solution {
    public int minMoves2(int[] nums) {

        int totalMoves = 0;

        java.util.Arrays.sort(nums); // this is dual pivot quick sort in jdk so. And this is not a sorting problem

        int medianIndex = (nums.length - 1) / 2;
        int median = nums[medianIndex];

        for (int i = 0; i < nums.length; i++) {
            int num = nums[i];
            int moves = (median >= num) ? median - num : num - median;
            totalMoves += moves;
        }

        return totalMoves;

    }
}
```