# Given a positive integer num, write a function which returns True if num is a perfect square else False.

**Note: Do not** use any built-in library function such as sqrt.

Example 1:
```
Input: 16
Output: true
Example 2:
```
```
Input: 14
Output: false
```

### Code
```csharp
public class Solution {
    public bool IsPerfectSquare(int num) {
     for(int i = 1 ;num/i>i-1;i++)
         if(num/i==i && num%i==0)
             return true;
        return false;
    }
}
```

#### Runtime: 40 ms, faster than 44.49% of C# online submissions for Valid Perfect Square.
#### Memory Usage: 12.5 MB, less than 100.00% of C# online submissions for Valid Perfect Square.
