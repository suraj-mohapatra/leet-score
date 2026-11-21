This solution follows the same two-pointer approach used in 3Sum. However,
instead of finding an exact triplet sum, we track the triplet whose sum is
closest to `target`.

After sorting the array, fix one value and use two pointers to find the remaining
pair. For each pair, calculate the absolute difference between its sum and the
target. The sum with the smallest absolute difference becomes the closest result.
If two sums are equally close, both are valid because they have the same absolute
difference from the target.

```
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);

        int closest = nums[0] + nums[1] + nums[2];

        for (int i = 0; i < nums.length - 2; i++) {

            int target1 = target - nums[i];

            int p1 = i + 1;
            int p2 = nums.length - 1;

            while (p1 < p2) {
                int sum = nums[p1] + nums[p2];

                int currentSum = nums[i] + sum;
                
                if (Math.abs(target1 - sum) < Math.abs(target - closest)) {
                    closest = currentSum;
                }

                if (sum < target1) {
                    p1++;
                } else if (sum > target1) {
                    p2--;
                } else {
                    return target;
                }
            }
        }

        return closest;
    }
}
```