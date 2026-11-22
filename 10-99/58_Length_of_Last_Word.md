first I did this.but my coder spirit does not allow me to stick to this g** solution


```
class Solution {
    public int lengthOfLastWord(String s) {

        String[] words = s.trim().split("\\s+");

        return words[words.length - 1].length();

    }
}
```


below is not the best solution either. it's a bunch of bulls**t.. After I did these 2 solutions I asked copilot if there exists any other solution. it suggested me to start wotht he last index.. I got his point. since i am tired now, I will do that later by my self.

```
class Solution {
    public int lengthOfLastWord(String s) {

        //s.trim()// I am deliberately not using this bcz my coder spirit kills me inside

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