```
class Solution {
    public int[] productExceptSelf(int[] nums) {
        var mul = 1; // extra O(1)
        var prefix_prod_arr = new int[nums.length]; //output space O(N)

        for (int i = 0; i < nums.length; i++) {
            mul *= nums[i];
            prefix_prod_arr[i] = mul;
        }

        mul = 1;// reusing the same sapce

        for (int i = nums.length - 1; i >= 0; i--) {
            int mul2 = (i == 0) ? 1 : prefix_prod_arr[i - 1];
            prefix_prod_arr[i] = mul2 * mul;
            mul *= nums[i];
        }

        return prefix_prod_arr;

    }
}
```