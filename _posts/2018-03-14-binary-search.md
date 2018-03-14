---
layout:     post
title:      二分查找（折半查找）
date:       2018-03-14 00:00:00
author:     Joy Zheng
summary:    二分查找算法
comments:   true
categories: Tech
thumbnail:  cogs
tags:
 - algorithm
---
#####基本思想：

 1. 二分查找的前提是在有序元素列中进行查询，所以取元素列中间的元素`array[mid]`与要查找的元素比较。
 2. 如果查找的元素比中间位小（or大），则在中间位的左（or右）半段查找。
 3. 循环步骤1直到元素列头部与尾部重合

#####代码实现：

    //递归
    public static int rec(int left, int right, int[] array, int data) {
        if (left <= right) {
            int mid = (left + right) >> 1;                     //取中间元素
            if (array[mid] == data) {
                return mid;
            } else if (array[mid] > data) {                    //检索元素在mid左
                return rec(left, mid - 1, array, data);        //从左半段查找
            } else if (array[mid] < data) {                    //检索元素在mid右
                return rec(mid + 1, right, array, data);       //从右半段查找
            }
        }
        return -1;
    }

    //非递归（推荐）
    public static int nonRec(int left, int right, int[] array, int data) {
        while (left <= right) {
            int mid = (left + right) >> 1;     //取中间元素
            if (array[mid] == data) {
                return mid;
            } else if (array[mid] > data) {     //检索元素在mid左
                right = mid -1;                 //从左半段查找
            } else if (array[mid] < data) {     //检索元素在mid右
                left = mid + 1;                 //从右半段查找
            }
        }
        return -1;
    }

  时间复杂度：O(logn)
  
  空间复杂度：递归O(logn)，非递归O(1)



