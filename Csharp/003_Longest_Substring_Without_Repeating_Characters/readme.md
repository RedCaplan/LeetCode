Given a string, find the length of the longest substring without repeating characters.

Example 1:
```
Input: "abcabcbb"
Output: 3 
Explanation: The answer is "abc", with the length of 3. 
```
Example 2:
```
Input: "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```
Example 3:
```
Input: "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3. 
             Note that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

### Code
```csharp
public class Solution {
    public int LengthOfLongestSubstring(string s) {
         int answer = 0;
        string s2 = "";
            for (int i = 0; answer < s.Length-i; i++)
            {                
                s2 ="" + s[i];

                for (int j = i + 1; j < s.Length; j++)
                {
                    if (s2.IndexOf(s[j]) == -1)
                        s2+=s[j];
                    else break;
                }

                answer=Math.Max(answer, s2.Length);
               
            }
        return answer;
    }
}
```
