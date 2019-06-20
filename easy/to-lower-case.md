## Problem

mplement function ToLowerCase() that has a string parameter str, and returns the same string in lowercase.

Example 1:

Input: "Hello"
Output: "hello"

Example 2:

Input: "here"
Output: "here"

Example 3:

Input: "LOVELY"
Output: "lovely"

## Solution

```java
class Solution {
    public String toLowerCase(String str) {
        char[] s = str.toCharArray();
        
        for (int i = 0; i < str.length(); i++)
            for (int j = 65; j <= 90; j++)
                if ( s[i] == (char)j ) s[i] = (char)(j+32);
        
        return String.valueOf(s);
    }
    
}
```