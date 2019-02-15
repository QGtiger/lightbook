## 冒泡排序

>冒泡排序顾名思义就是整个过程像个气泡一样上升:对于给定的n个数据，从一个数据开始依次比较，第一轮比较后n个数据中最大数据就是在n位置上

## 代码展示

```
def bubble_sort(lists):
    count = len(lists)
    for i in range(count-1):
        for j in range(i+1,count):
            if lists[j]<lists[i]:
                temp = lists[i]
                lists[i] = lists[j]
                lists[j] = temp
    return lists

if __name__ == '__main__':
    lists = [13, 65, 97, 76, 38, 27, 49]
    print('排序前: ')
    for i in range(len(lists)):
        print(lists[i], end=" ")
    print('\n排序后: ')
    re_lists = bubble_sort(lists=lists)
    for i in range(len(re_lists)):
        print(re_lists[i], end=" ")
```

## 性能分析

冒泡排序是一种稳定的排序方法，最好的时间复杂度为O(N),最坏和平均时间复杂度为O(n^2)，空间复杂度为O(1)