Given an array of 4 digits, return the largest 24 hour time that can be made.

The smallest 24 hour time is 00:00, and the largest is 23:59.  Starting from 00:00, a time is larger if more time has elapsed since midnight.

Return the answer as a string of length 5.  If no valid time can be made, return an empty string.

Example 1:
```
Input: [1,2,3,4]
Output: "23:41"
```

Example 2:
```
Input: [5,5,5,5]
Output: ""
```
Note:
* A.length == 4
* 0 <= A[i] <= 9


### Code
#### Needs a total makeover.
```csharp
public class Solution {
        public static int RemoveAndGetItem(ref List<int> list, int MaxValue)
        {
            int value = (from x in list where x <= MaxValue select x).Max();
            list.Remove(value);
            return value;
        }

        public static string FindMaxTime(int[] A)
        {
            var list = A.ToList();
            try
            {
                int hourFirst;
                int hourSecond;
                int minFirst;
                int minSecond;


                hourFirst = RemoveAndGetItem(ref list, 2);

                if (hourFirst == 2)
                    hourSecond = RemoveAndGetItem(ref list, 3);
                else
                    hourSecond = RemoveAndGetItem(ref list, 9);


                minFirst = RemoveAndGetItem(ref list, 5);

                minSecond = RemoveAndGetItem(ref list, 9);

                return $"{hourFirst}{hourSecond}:{minFirst}{minSecond}";
            }
            catch
            {
                return "";
            }
        }


        public static string FindMinTime(int[] A)
        {
            var list = A.ToList();
            try
            {
                int hourFirst;
                int hourSecond;
                int minFirst;
                int minSecond;

                hourSecond = RemoveAndGetItem(ref list, 9);

                if(hourSecond>3)
                    hourFirst = RemoveAndGetItem(ref list, 1);
                else
                    hourFirst = RemoveAndGetItem(ref list, 2);



                minFirst = RemoveAndGetItem(ref list, 5);

                minSecond = RemoveAndGetItem(ref list, 9);

                return $"{hourFirst}{hourSecond}:{minFirst}{minSecond}";
            }
            catch
            {
                return "";
            }
        }



       public string LargestTimeFromDigits(int[] A)
        {
            string answer = FindMaxTime(A);
            return answer == "" ? FindMinTime(A) : answer;
         }

}
```

