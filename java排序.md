# java排序

## 排序的分类
1. 内部排序法
指将需要处理的所有数据都加载到内部存储器中进行排序。包括(交换式排序法、选择式排序法和插入式排序法)；

2. 外部排序法
数据量过大， 无法全部加载到内存中， 需要借助外部存储进行排序。包括(合并排序法和直接合并排序法)。


## 交换式排序
交换式排序属于内部排序法是运用数据值比较后， 依判断规则对数据位置进行交换，以达到排序的目的。

交换式排序法又可分为两种：
1. 冒泡排序法(Bubble Sorting)
2. 快速排序法(Quick Sorting)

交换式排序法-- 冒泡排序法
冒泡排序(Bubble Sorting) 的基本思想是：
通过对待排序序列从后向前(从下标较大的元素开始)，依次比较相邻元素的排序码，若发现逆序则交换，使排序码较小的元素逐渐从
后部移向前部(从下标较大的单元移向下标较小的单元)，就象水底下的气泡一样逐渐向上冒。

因为排序的过程中，各元素不断接近自己的位置，如果一趟比较下来没有进行过交换，
就说明序列有序，因此要在排序过程中设置一个标志flag 判断元素是否进行过交换。从而减少不必要的比较。
```java
package com.liu.test;

public class BubbleSorting {
	public static void main(String[] args) {
		int arr[] = { 1, 6, 0, -1, 9, -100, 90 };
		int temp = 0;
// 排序
// 外层循环，可以决定一共走趟
		for (int i = 0; i < arr.length - 1; i++) {
// 内层循环，开始逐个比较，如果发现前一个数比后一个数大则交换
			for (int j = 0; j < arr.length - 1 - i; j++) {
				if (arr[j] > arr[j + 1]) {
// 换位
					temp = arr[j];
					arr[j] = arr[j + 1];
					arr[j + 1] = temp;
				}
			}
		}
// 输出最后结果
		for (int i = 0; i < arr.length; i++) {
			System.out.print(arr[i] + "\t");
		}
	}
}
```
