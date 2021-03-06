# 如何从大量的url中找到相同的url

## 问题描述

>给定a、b两个文件，各存放50亿个url，每个url各占64B，内存限制是4GB，请找出a、b两个文件共同的url

## 分析解答

>由于每个url各占64B，所以50亿各url占用空间的大小为50亿×64 = 5GB×64 = 320GB。由于内存只有4GB，因此不可能一次性把所有的url都加载到内存中进行处理。所以，对于这种类型的题目，一般使用的是分治法，即把一个文件的url按照某一特性分成多个文件，使得每个文件的内容都小于4GB