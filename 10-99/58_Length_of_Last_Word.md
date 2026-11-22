```
class Solution {
    public int lengthOfLastWord(String s) {

        //s.trim()// I am deliberately not using this

        int count = 0;
        int lastWordLength = 0;

        for (int i = 0; i < s.length(); i++) {

            if (s.charAt(i) == ' ') {
                if (count > 0) {
                    lastWordLength = count;
                }
                count = 0;
            } else {
                count++;
            }
        }

        if (s.charAt(s.length() - 1) != ' ') {
            lastWordLength = count;
        }

        return lastWordLength;
    }
}
```

super quick
```
class Solution {
    public int lengthOfLastWord(String s) {

        String[] words = s.trim().split("\\s+");

        return words[words.length - 1].length();

    }
}
```