```
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {

        ListNode dummy = new ListNode();

        var tail = dummy;
        var curr1 = list1;
        var curr2 = list2;

        while (curr1 != null && curr2 != null) {

            if (curr1.val <= curr2.val) {
                tail.next = curr1;
                curr1 = curr1.next;
                tail = tail.next;

            } else {

                tail.next = curr2;
                curr2 = curr2.next;
                tail = tail.next;

            }

        }

        if (curr1 != null) {
            tail.next = curr1;

        } else if (curr2 != null) {
            tail.next = curr2;

        }

        return dummy.next;

    }
}
```