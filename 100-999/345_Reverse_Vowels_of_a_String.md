```
class Solution {
    public String reverseVowels(String s) {

        char[] arr = s.toCharArray();

        int left = 0;
        int right = arr.length - 1;

        while (left < right) {
            boolean isLeftVowel = isVowel(arr[left]);
            boolean isRightVowel = isVowel(arr[right]);

            if (isLeftVowel && isRightVowel) {
                char temp = arr[left];
                arr[left] = arr[right];
                arr[right] = temp;

                left++;
                right--;

            } else if (isLeftVowel && !isRightVowel) {
                right--;

            } else if (!isLeftVowel && isRightVowel) {
                left++;

            } else if (!isLeftVowel && !isRightVowel) {
                left++;
                right--;
            }
        }

        return new String(arr);

    }

    private static boolean isVowel(char c) {
        return "aeiouAEIOU".indexOf(c) != -1;
    }
}
```


another isVowel implementation is... this is faster

```
    private static boolean isVowel(char c) {
        return c == 'a' || c == 'e' || c == 'i' ||
                c == 'o' || c == 'u' ||
                c == 'A' || c == 'E' || c == 'I' ||
                c == 'O' || c == 'U';
    }
}
```