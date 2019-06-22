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