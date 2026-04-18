


```
class Solution {
    public String longestCommonPrefix(String[] strs) {

        if (strs == null || strs.length == 0) return "";

        int first_string_size = strs[0].length();
        int curr_min_size = first_string_size;

        for (int i = 0; i < strs.length; i++) {
            if (strs[i].length() < curr_min_size) {
                curr_min_size = strs[i].length();
            }
        }

        StringBuffer rslt = new StringBuffer();

        for (int z = 0; z < curr_min_size; z++) {

            char currChar = strs[0].charAt(z);

            for (int i = 0; i < strs.length; i++) {

                if (strs[i].charAt(z) != currChar) {
                    return rslt.toString();
                }
            }

            rslt.append(currChar);
        }

        return rslt.toString();
    }
}

```
