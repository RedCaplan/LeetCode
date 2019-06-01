You are given a string, s, and a list of words, words, that are all of the same length. 
Find all starting indices of substring(s) in s that is a concatenation of each word in words exactly once and without any intervening characters.

Example 1:
```
**Input:**
  **s** = "barfoothefoobarman",
  **words** = ["foo","bar"]
**Output**: [0,9]
**Explanation:** Substrings starting at index 0 and 9 are "barfoor" and "foobar" respectively.
The output order does not matter, returning [9,0] is fine too.
```
Example 2:
```
**Input:**
  **s** = "wordgoodgoodgoodbestword",
  **words** = ["word","good","best","word"]
**Output**: []
```



### Code
```csharp
public class Solution {
    public IList<int> FindSubstring(string s, string[] words) {
           if (s.Length == 0 || words.Length==0 || 
                s.Length < words.Length) return new List<int>();

            int wordLength = words[0].Length;


            IList<int> answer = new List<int>();


            Dictionary<string,int> dictionary = words.Distinct().ToDictionary(item => item,
                item => words.Count(x => x == item));
        

            for (int i = 0; i < s.Length; i++)
            {
            
                if (words.Any(x => x[0] == s[i]))
                {
                    Dictionary<string, int> copyDictionary  = new Dictionary<string, int>(dictionary);


                    if (i + wordLength * words.Length > s.Length)
                        break;

                    string substr = s.Substring(i, wordLength * words.Length);
                    int counter = 0;

                    for (int j = 0; j < words.Length; j++)
                    {
                        if (i + j * wordLength + wordLength > s.Length)
                            break;

                        string word = substr.Substring(j * wordLength, wordLength);
                        if (!copyDictionary.ContainsKey(word))
                            break;

                        copyDictionary[word]--;

                        if (copyDictionary.Any(x => x.Value < 0))
                            break;
                        counter++;
                    }
            if (copyDictionary.Count(x => x.Value != 0)==0)      
                        answer.Add(i);
                }
            }
            return answer;
    }
}
```
