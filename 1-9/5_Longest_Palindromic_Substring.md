https://www.geeksforgeeks.org/dsa/longest-palindromic-substring/

```
class Solution {
    public String longestPalindrome(String s) {
        int len = s.length();
        int maxLen = 1; //bcz in theworst case the maximum leght is a single character so it will be 1
        int start = 0;
        for(int i=0;i<len;i++){
            for(int j = i;j<len;j++){
              if(checkPal(s,i, j) && j-i+1 > maxLen){

                maxLen = j-i+1;
                start = i;
               }
               
            }          
        }
        return s.substring(start, start + maxLen);
    }

    private boolean checkPal(String s, int low, int high){ // takes the string, lower and upper bounds
        while (low < high) {
            if (s.charAt(low) != s.charAt(high))
                return false;
            low++;
            high--;
        }
        return true;        
    } 
}
```



```
class Solution {
    public String longestPalindrome(String s) {
        int n = s.length();

        boolean[][] dp = new boolean[n][n];

        int start = 0;
        int maxLength = 1;

        // Every single character is a palindrome
        for (int i = 0; i < n; i++) {
            dp[i][i] = true;
        }

        // Check substrings by increasing length
        for (int length = 2; length <= n; length++) {

            for (int i = 0; i <= n - length; i++) {

                int j = i + length - 1;

                if (s.charAt(i) == s.charAt(j)) {

                    // Length 2: just need the two characters to match
                    if (length == 2) {
                        dp[i][j] = true;
                    }
                    // Length >= 3: check whether the inside is a palindrome
                    else {
                        dp[i][j] = dp[i + 1][j - 1];
                    }
                }

                // Update longest palindrome
                if (dp[i][j] && length > maxLength) {
                    start = i;
                    maxLength = length;
                }
            }
        }

        return s.substring(start, start + maxLength);
    }
}
```
