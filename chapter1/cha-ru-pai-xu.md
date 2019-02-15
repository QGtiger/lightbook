## 插入排序

>对于给定的一组数据，初始时假定第一个数据自成一个有序数列，其余的数据为无序序列；接着第二个数据开始按照大小一次将当前处理数据插入到其之前的有序序列中。直到最后一个数据插入到有序序列中

## 代码展示

```
def insert_sort(lists):
    count = len(lists)
    for i in range(1,count):
        key = lists[i]
        j = i-1
        while j >= 0:
            if lists[j]>key:
                lists[j+1] = lists[j]
                lists[j] = key
            j -= 1
    return lists

if __name__ == '__main__':
    lists = [13, 65, 97, 76, 38, 27, 49]
    print('排序前: ')
    for i in range(len(lists)):
        print(lists[i], end=" ")
    print('\n排序后: ')
    re_lists = insert_sort(lists=lists)
    for i in range(len(re_lists)):
        print(re_lists[i], end=" ")
```

## 性能分析

插入排序是一种稳定的排序方法，最好的时间复杂度为O(N),最坏和平均时间复杂度为O(n^2)，空间复杂度为O(1)