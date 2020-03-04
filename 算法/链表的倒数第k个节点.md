思路： 首先是边界判断，其次采用快慢指针的方式，快指针先移动k步，之后慢指针开始移动，当快指针指向null时，慢指针指到返回节点。  

```Java
//public class ListNode{
//	int val;
//	ListNode next = null;
//	
//	ListNode(int val){
//		this.val = val;
//	}
//}

class Solution {
    
	public ListNode FindKthToTail(ListNode head, int k) {
		if(head == null || k <= 0) {
			return null;
		}
		int step = 0;
		ListNode fast = head;
		ListNode slow = head;
		while(step<k) {
			if(fast==null) {
				return null;
			}
			fast = fast.next;
			step++;
		}
		while(fast!=null) {
			fast = fast.next;
			slow = slow.next;
		}
		return slow;
	}
}
```