
Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

**Note:**

* The number of elements initialized in nums1 and nums2 are m and n respectively.
* You may assume that nums1 has enough space (size that is greater or equal to m + n) to hold additional elements from nums2.

Example:
```
Input:
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6],       n = 3

Output: [1,2,2,3,5,6]
``` 


### Code
```csharp
public class Solution {
    public void Merge(int[] nums1, int m, int[] nums2, int n) {
        int index1 = m-1;
        int index2 = n-1;
        
        int length = n+m-1;
        
       while(index1 > -1 && index2 > -1){
            if(nums1[index1] == nums2[index2]){
               nums1[length--]=nums1[index1--];
               nums1[length--]=nums2[index2--];
                    continue;
           }
            nums1[length--] = nums1[index1] >= nums2[index2]?nums1[index1--]:nums2[index2--];
       }
           
        while(index1 > -1)
            nums1[length--] = nums1[index1--];
        
        while(index2 > -1)
            nums1[length--] = nums2[index2--];
      
    }
}
```
