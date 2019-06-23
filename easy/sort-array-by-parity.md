## Problem

Given an array A of non-negative integers, return an array consisting of all the even elements of A, followed by all the odd elements of A.

You may return any answer array that satisfies this condition.

Example 1:

Input: [3,1,2,4]
Output: [2,4,3,1]
The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.

Note:

    1 <= A.length <= 5000
    0 <= A[i] <= 5000

## Solution

```java
class Solution {
    public int[] sortArrayByParity(int[] A) {
        int p = 0, s = A.length - 1;
        int[] B = new int[A.length];
        
        for (int i = 0; i < A.length; i++) {
            if ( (A[i]%2) == 0 ) B[p++] = A[i];
            else B[s--] = A[i];
        }
        
        return B; 
    }
}
```