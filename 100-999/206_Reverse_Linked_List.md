```
class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;
        ListNode next = null;

        //if(curr == null) return null;

        while(curr!= null){
            next = curr.next; // extracted the next as curr gonna chanege
            curr.next = prev; // reverse pointed
            prev = curr; // for next iteration present curr will be prev
            curr = next; // for next iteration present curr's next will be curr
        }

        return prev;      
        
    }
}
```