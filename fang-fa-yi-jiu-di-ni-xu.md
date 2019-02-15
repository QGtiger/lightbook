# 主要思路

>在遍历链表的时候，修改当前节点的指针域的指向，让其指向它的前驱节点。为此，需要用一个指针用来保存当前前驱结点的地址。此外，为了调整当前节点指针域的指向后还能找到后继节点，还需要一个指针变量来保存后继节点的地址。

## 实现代码

```
class Node:
    def __init__(self):
        self.data = None
        self.next = None

def Reverse(head):
    # 判断链表是否为空
    if head == None or head.next == None:
        return
    pre = None # 前驱结点
    cur = None # 当前节点
    next = None # 后继节点
    # 把链表首节点变为尾结点
    cur = head.next
    next = cur.next
    cur.next = None
    pre = cur
    cur = next
    while cur.next != None:
        next = cur.next
        cur.next = pre
        pre = cur
        cur = next
    # 链表最后一个节点指向倒数第二个
    cur.next = pre
    # 链表头结点指向原来链表的尾结点
    head.next = cur

if __name__ == '__main__':
    i = 1
    head = Node()
    head.next = None
    tmp = None
    cur = head
    while i < 8:
        tmp = Node()
        tmp.data = i
        tmp.next = None
        cur.next = tmp
        cur = tmp
        i += 1
    print('逆序前: ',end=" ")
    cur = head.next
    while cur != None:
        print(cur.data,end='->'if cur.next!=None else '')
        cur = cur.next

    print('\n逆序后: ',end=" ")
    Reverse(head)
    cur = head.next
    while cur!=None:
        print(cur.data, end='->' if cur.next != None else '')
        cur = cur.next
```

## 成功截图

![img](http://qnpic.top\reverse%20link%5C1.jpg)

## 算法性能分析

>这种方法只需要对链表进行一次遍历，因此时间复杂度为 `O(N)`,空间复杂度为`O(1)`