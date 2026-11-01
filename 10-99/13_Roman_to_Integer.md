```
class Solution:
    def romanToInt(self, s: str) -> int:
        rval = {
            'I': 1,
            'V': 5,
            'X': 10,
            'L': 50,
            'C': 100,
            'D': 500,
            'M': 1000
        }

        i = 0
        result = 0

        while i < len(s):
            if i < len(s) - 1 and rval[s[i]] < rval[s[i+1]]:
                result += rval[s[i+1]] - rval[s[i]]
                i += 2
            else:
                result += rval[s[i]]
                i += 1

        return result
```



```
class Solution {
    public int romanToInt(String s) {
        Map<Character, Integer> rval = Map.of(
                'I', 1, 'V', 5, 'X', 10, 'L', 50,
                'C', 100, 'D', 500, 'M', 1000);

        int result = 0, i = 0;

        while (i < s.length()) {
            if (i < s.length() - 1 && rval.get(s.charAt(i)) < rval.get(s.charAt(i + 1))) {
                result += rval.get(s.charAt(i + 1)) - rval.get(s.charAt(i));
                i += 2;
            } else {
                result += rval.get(s.charAt(i));
                i++;
            }
        }

        return result;

    }
}
```