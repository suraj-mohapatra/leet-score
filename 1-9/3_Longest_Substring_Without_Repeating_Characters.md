```
class Solution {
    public int lengthOfLongestSubstring(String s) {
        int n = s.length();
        int maxLength = 0;
        HashMap<Character, Integer> map = new HashMap<>(); 

        for (int j = 0, i = 0; j < n; j++) {
            if (map.containsKey(s.charAt(j))) {
                i = Math.max(map.get(s.charAt(j)) + 1, i);
                //i = map.get(s.charAt(j)) + 1;
            }
            map.put(s.charAt(j), j);
            maxLength = Math.max(maxLength, j - i + 1);
        }
        return maxLength;
    }
}
```