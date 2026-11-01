```
class Solution {
    public int reverse(int x) {

        int num = x;

        int reverse = 0;

        while (num != 0) { //123

            int r = num % 10;

            // Overflow check
            if (reverse > Integer.MAX_VALUE / 10 || (reverse == Integer.MAX_VALUE / 10 && r > 7)) {
                return 0;
            }

            if (reverse < Integer.MIN_VALUE / 10 || (reverse == Integer.MIN_VALUE / 10 && r < -8)) {
                return 0;
            }

            reverse = reverse * 10 + r;

            int q = num / 10;

            num = q;

        }

        return reverse;

    }
}
```