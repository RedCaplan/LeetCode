You are given two **non-empty** linked lists representing two non-negative integers. The digits are stored in **reverse order** and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example:
```
Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.
```

### Code
```csharp
public class Solution {
    public ListNode AddTwoNumbers(ListNode l1, ListNode l2) {
            ListNode answer= new ListNode(0);
            ListNode tail=answer;
            int remainder=0;
            while (l1 != null || l2 !=null ) {
                int num1 = l1!=null?l1.val:0;
                int num2 = l2!=null?l2.val:0;
                
                int sum=num1+num2+remainder;
                tail.next = new ListNode(sum%10);
                tail=tail.next;
                
                remainder=sum/10;
                
                l1= l1!=null?l1.next:null;
                l2= l2!=null?l2.next:null;
            }
        if(remainder!=0)
            tail.next= new ListNode(remainder);
            
            return answer.next;
    }
}
```
