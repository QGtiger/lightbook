## 归并排序

>归并排序就是利用递归和分治技术将数据序列分成为越来越来小的半子集，在对半子集排序，最后再用递归步骤将排好序的半子集合并成为越来越大的有序排序。其中'归'代表着‘递归’，即递归地将数组折半地分离为单个数组；例如：数组[2,6,1,0]会先折半成[2,6]和[1,0],然后再折半将数组分离，分为[2]，[6]，[1]，[0]。并就是将分开的数据从小到大或者从大到小的顺序放到一个数组中，如上面的[2],[6]合并到一个数组就是[2,6].[1],[0]合并到一个数组中就是[0,1],然后将[2,6],[0,1]合并成一个数组，即为[0,1,2,6]

## 代码展示

```
def merge(left,right):
    i,j = 0,0
    result = []
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i+=1
        else:
            result.append(right[j])
            j+=1
    result += left[i:]
    result += right[j:]
    return result

def merge_sort(lists):
    if len(lists)<=1:
        return lists
    num = int(len(lists)/2)
    left = merge_sort(lists[:num])
    right = merge_sort(lists[num:])
    return merge(left,right)

if __name__ == '__main__':
    lists = [13,65,97,76,38,27,49]
    print('排序前: ')
    for i in range(len(lists)):
        print(lists[i],end=" ")
    print('\n排序后: ')
    re_lists = merge_sort(lists=lists)
    for i in range(len(re_lists)):
        print(re_lists[i],end=" ")
```

## 性能分析

二路归并排序的过程需要logn次，每一趟归并排序的操作，就是把将两个有序子序列进行归并。而每一对有序子序列归并时，记录的比较次数小于等于数据的移动次数，每一趟归并的时间复杂度为O(N)。因此二路归并排序在最好、最坏和平均情况的时间复杂度为O(nlogn),而且是一种稳定的排序方法。空间复杂度为O(1)