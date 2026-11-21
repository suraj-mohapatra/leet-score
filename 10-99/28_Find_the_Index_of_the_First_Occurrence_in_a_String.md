This solution uses a brute-force approach. For each valid starting position in `haystack`, it compares the substring of the same length with `needle`. It returns the first matching index and `-1` if no match is found.

The LeetCode hints include Two Pointers, String, String Matching, Z Algorithm, Knuth–Morris–Pratt (KMP), and Boyer–Moore. Brute force is also an accepted and straightforward solution for this problem.

```
class Solution {
    public int strStr(String haystack, String needle) {

        int index = -1; //starting with default value assumig there are no match yet

        for (int i = 0; i <= haystack.length() - needle.length(); i++) {

            int j;

            for (j = 0; j < needle.length(); j++) {
                if (needle.charAt(j) != haystack.charAt(i + j)) {
                    break;
                }
            }

            if (j == needle.length()) {
                index = i;
                break;
            }
        }

        return index;
    }
}
```