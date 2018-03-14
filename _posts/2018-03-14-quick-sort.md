---
layout:     post
title:      快速排序
date:       2018-03-14 00:00:00
author:     Joy Zheng
summary:    快速排序算法
comments:   true
categories: Tech
thumbnail:  cogs
tags:
 - algorithm
---
#### 基本思想：

 1. 在`R[low..high]`中任选一个记录作为基准(Pivot)。
 2. 以此基准将当前无序区划分为左、右两个较小的子区间`R[low..pivotPos-1)`和`R[pivotPos+1..high]`，并使左边子区间中所有记录的关键字均小于等于基准记录(不妨记为pivot)的关键字`pivot.key`，右边的子区间中所有记录的关键字均大于等于`pivot.key`。
 3. 而基准记录pivot则位于正确的位置`pivotpos`上。
 4. 然后分别对这两部分记录用同样的方法继续进行排序，直到整个序列有序。

#### 代码实现：

    private static int partition(int[] list, int left, int right) {
        int key = list[left];

        while (left < right) {
            while (list[right] >= key && left < right) {
                right--;
            }
            list[left] = list[right];
            while (list[left] <= key && left < right) {
                left++;
            }
            list[right] = list[left];
        }
        list[right] = key;
        return right;
    }
   
    //递归实现
    private static void quickSort_rec(int[] list, int left, int right) {
        if (left < right) {
            int pivot = this.partition(list, left, right);
            this.quickSort_rec(list, left, pivot - 1);
            this.quickSort_rec(list, pivot + 1, right);
        }
    }

    //非递归实现
    private static void quickSort_nonRec(int[] a,int start,int end) {
        Stack<Integer> stack = new Stack<>();  //用栈模拟
        if(start < end) {
            stack.push(end);
            stack.push(start);
            while(!stack.isEmpty()) {
                int l = stack.pop();
                int r = stack.pop();
                int pivot = partition(a, l, r);
                if(l < pivot - 1) {
                    stack.push(pivot-1);
                    stack.push(l);
                }
                if(r > pivot + 1) {
                    stack.push(r);
                    stack.push(pivot+1);
                }
            }
        }
    }

时间复杂度：

  * 最优情况：O(nlogn)

  * 最差情况：O(n^2) ※每一次取到的元素就是数组中最小/最大的，这种情况其实就是冒泡排序了(每一次都排好一个元素的顺序)

  * 平均：O(nlogn) 

空间复杂度：

  * 最优情况：O(logn)※每一次都平分数组的情况

  * 最差情况：O(n)※退化为冒泡排序的情况

稳定性：
  * 不稳定



