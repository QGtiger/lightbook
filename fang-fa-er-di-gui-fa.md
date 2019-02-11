# 递归法

>假定原链表为 1->2->3->4->5,递归法的主要思路为：先逆序除第一个节点以外的子链表(将1->**2**->**3**->**4**->**5**变成 1->5->4->3->2),接着将节点1添加到这个子链表的后面，即 1->5->4->3->2 变成 5->4->3->2->1。同理，逆序链表 2->3->4->5时，也是先逆序子链表3->4->5（逆序为2->5->4->3）,然后又把2节点换到最后....实现代码如下

# 实现代码：

```
class Node:
    def __init__(self):
        self.data = None
        self.next = None

"""
对不带头结点的简单单链表进行逆序
"""
def RecursiveReverse(head):
    if head is None or head.next == None:
        return head
    else:
        # 反转后面子链表
        newhead = RecursiveReverse(head.next)
        # 把当前遍历的节点加到逆序后的链表尾部
        head.next.next = head
        head.next = None
    return newhead
```

# 算法分析

>递归法也是对链表遍历了一遍，因此时间复杂度为O(N), 思路直观，容易理解。缺点就是需要额外的压栈和弹栈操作，性能会有所下降