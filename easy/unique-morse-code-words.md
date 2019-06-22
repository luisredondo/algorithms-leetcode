## Problemn

International Morse Code defines a standard encoding where each letter is mapped to a series of dots and dashes, as follows: "a" maps to ".-", "b" maps to "-...", "c" maps to "-.-.", and so on.

For convenience, the full table for the 26 letters of the English alphabet is given below:

[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]

Now, given a list of words, each word can be written as a concatenation of the Morse code of each letter. For example, "cba" can be written as "-.-..--...", (which is the concatenation "-.-." + "-..." + ".-"). We'll call such a concatenation, the transformation of a word.

Return the number of different transformations among all words we have.

Example:
Input: words = ["gin", "zen", "gig", "msg"]
Output: 2
Explanation: 
The transformation of each word is:
"gin" -> "--...-."
"zen" -> "--...-."
"gig" -> "--...--."
"msg" -> "--...--."

There are 2 different transformations, "--...-." and "--...--.".

Note:

    The length of words will be at most 100.
    Each words[i] will have length in range [1, 12].
    words[i] will only consist of lowercase letters

## Solution

```java
class Solution {
    public int uniqueMorseRepresentations(String[] words) {
         
        Set<String> arr = new HashSet<String>(Arrays.asList( getMorseCode( words ) ));
  
        return arr.size();
    }
    
    public String[] getMorseCode(String[] words) {
        
        String[] code = new String[ words.length ];
        String[] morse = { ".-", "-...", "-.-.", "-..", ".", "..-.", "--.", "....", "..", ".---", "-.-", ".-..", "--", "-.", "---", ".--.", "--.-", ".-.", "...", "-", "..-", "...-", ".--", "-..-", "-.--", "--.." };        
        
        for (int i = 0; i < words.length; i++)
            for (char s: words[i].toCharArray() )           
                for (int j = 97; j <= 122; j++)        
                    if ( s == (char) j ) {
                        if ( code[i] == null ) code[i] = "";
                        code[i] += morse[j - 97];  
                    } 
          
        return code;
    }
                
}
```