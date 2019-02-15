## 快速排序

>快速排序是一种非常高效的排序算法，它采用“分而治之”的思想，大大的拆分为小的，小的再拆分为更小的。其原理是：对于一组给定的数据，通过一趟排序，将原序列分为两个部分，其中前部分的所有数据均比后部分的数据小，然后在依次对前后部分进行快速排序，递归该过程，知道所有数据都有序为止。

## 代码展示

```
def quick_sort(lists,left,right):
    if left >= right:
        return lists
    key = lists[left]
    low = left
    high = right
    while left < right:
        while left < right and lists[right] >= key:
            right -= 1
        lists[left] = lists[right]
        while left < right and lists[left] <= key:
            left += 1
        lists[right] = lists[left]
    lists[right] = key
    quick_sort(lists,low,left-1)
    quick_sort(lists,left+1,high)
    return lists

if __name__ == '__main__':
    lists = [13, 65, 97, 76, 38, 27, 49]
    print('排序前: ')
    for i in range(len(lists)):
        print(lists[i], end=" ")
    print('\n排序后: ')
    re_lists = quick_sort(lists,0,len(lists)-1)
    for i in range(len(re_lists)):
        print(re_lists[i], end=" ")
```