## 选择算法

>选择排序算法是一种简单直观的算法，它的基本算法如下：对于给定的一组数据，经过第一轮比较后得到最小的数据，然后将该数据和第一个数据进行交换；接着对不包含第一个数据以外的其他数据进行第二轮比较，得到最小数据和第二个数据进行位置交换；重复该过程，知道进行比较的记录只有一个为止。

## 代码展示

```
def select_sort(lists):
    count = len(lists)
    for i in range(0,count):
        min = i
        for j in range(i+1,count):
            if lists[min]>lists[j]:
                min = j
        lists[min],lists[i] = lists[i],lists[min]
    return lists


if __name__ == '__main__':
    lists = [13,65,97,76,38,27,49]
    print('排序前: ')
    for i in range(len(lists)):
        print(lists[i],end=" ")
    print('\n排序后: ')
    re_lists = select_sort(lists=lists)
    for i in range(len(re_lists)):
        print(re_lists[i],end=" ")

```

## 性能分析

选择排序是一种不稳定的排序方法，实现复杂度为O(n^2),空间复杂度为O(1)