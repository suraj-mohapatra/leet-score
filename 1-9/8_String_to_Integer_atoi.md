```
class Solution {
    public int myAtoi(String s) {

        s = s.stripLeading();
        if (s.length() == 0) return 0;

        int sign = 1;
        int i = 0;
        long result = 0;

        if (s.charAt(i) == '-' || s.charAt(i) == '+') {
            sign = (s.charAt(i) == '-') ? -1 : 1;
            i++;
        }

        for (; i < s.length(); i++) {

            char c = s.charAt(i);

            if (!Character.isDigit(c))
                break;

            int digit = c - '0';
            result = result * 10 + digit;

            if (sign * result > Integer.MAX_VALUE)
                return Integer.MAX_VALUE;

            if (sign * result < Integer.MIN_VALUE)
                return Integer.MIN_VALUE;
        }

        return (int)(sign * result);
    }
}
```