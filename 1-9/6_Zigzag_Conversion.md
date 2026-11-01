```
class Solution {
    public String convert(String s, int numRows) {

        if (numRows == 1 || numRows >= s.length()) {
            return s;
        }

        StringBuilder[] rows = new StringBuilder[numRows];

        // I will create number of rows here
        for (int i = 0; i < numRows; i++) {
            rows[i] = new StringBuilder();
        }

        int row = 0;

        int direction = 1; // direction 1 for downward and -1 for upward.. initial direction is downward

        for (char c : s.toCharArray()) {
            rows[row].append(c);

            if (row == numRows - 1) { //3 say
                direction = -1; //flipping the direction to uoward
            }

            if (row == 0) {// when the row becomes again flip the direction to forward
                direction = 1;
            }

            row += direction;
        }

        StringBuilder result = new StringBuilder();

        for (StringBuilder r : rows) {
            result.append(r);
        }

        return result.toString();
    }
}
```