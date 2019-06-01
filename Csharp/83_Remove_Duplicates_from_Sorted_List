Given a sorted linked list, delete all duplicates such that each element appear only once.

Example 1:
```
Input: 1->1->2
Output: 1->2
```

Example 1:
```
Input: 1->1->2->3->3
Output: 1->2->3
```


### Code
```csharp
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     public int val;
 *     public ListNode next;
 *     public ListNode(int x) { val = x; }
 * }
 */
public class Solution {
    public ListNode DeleteDuplicates(ListNode head) {
        ListNode temp = head;
        while(temp!=null && temp.next != null){
            if(temp.val == temp.next.val){
                temp.next=temp.next.next;
                continue;
            }
            temp=temp.next;
        } 
        return head;
    }
}
```
