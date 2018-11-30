---
layout: post
title: leetcode习题
date: 2018-11-11
categories: 技术
---



### java版

1. 给定一个整数数组和一个目标值，找出数组中和为目标值的**两个**数。你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。**示例:**

   ```
   给定 nums = [2, 7, 11, 15], target = 9
   因为 nums[0] + nums[1] = 2 + 7 = 9
   所以返回 [0, 1]
   ```


2. (数组)给定一个非负整数数组 `A`，返回一个由 `A` 的所有偶数元素组成的数组，后面跟 `A` 的所有奇数元素。你可以返回满足此条件的任何数组作为答案，示例：

   ```
   输入：[3,1,2,4]
   输出：[2,4,3,1]
   输出 [4,2,3,1]，[2,4,1,3] 和 [4,2,1,3] 也会被接受。
   ```

   结果：

   ```java
   class Solution {
       public int[] sortArrayByParity(int[] A) {
           int[] b = new int[A.length];
           int m = 0,n = A.length -1;
           for (int i = 0; i < A.length; i++) {
   			if(A[i]%2 == 0) 
   				b[m++] = A[i];
   			else 
   				b[n--] = A[i];
   		}
           
           return b;
       }
   }
   ```

3. 给定一个整数数组 `A` ，考虑 `A` 的所有非空子序列。对于任意序列 S ，设 S 的宽度是 S 的最大元素和最小元素的差。返回 A 的所有子序列的宽度之和。由于答案可能非常大，请**返回答案模 10^9+7**。

   ```
   输入：[2,1,3]
   输出：6
   解释：
   子序列为 [1]，[2]，[3]，[2,1]，[2,3]，[1,3]，[2,1,3] 。
   相应的宽度是 0，0，0，1，1，2，2 。
   这些宽度之和是 6 。
   ```

   answer:

   ```java
   import java.util.Arrays;
   public class Solution {
   	public int sumSubseqWidths(int[] A) {
   		int mod = 1000000007;
           Arrays.sort(A);
           long ans = 0,pow2 = 1;
           for (int i = 0; i < A.length; i++) {
               ans = (ans + (A[i] - A[A.length-1-i]) * pow2)%mod;
               pow2 = (pow2<<1)%mod;
           }
           return (int)ans;
       }
   }
   ```


### C语言版

1. 给定一个整数数组和一个目标值，找出数组中和为目标值的**两个**数。你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。**示例:**

   ```
   给定 nums = [2, 7, 11, 15], target = 9
   因为 nums[0] + nums[1] = 2 + 7 = 9
   所以返回 [0, 1]
   ```

   answer:

   ```c
   int* twoSum(int* nums, int numsSize, int target) {
       int *nums1 = (int*)malloc(2*sizeof(int));
       for(int i = 0;i < numsSize;i++){
           nums1[0] = i;
           for(int j = i+1;j < numsSize;j++) {
               if (target - nums[i] == nums[j]) {
                   nums1[1] = j;
                   return nums1;
               }
           }
       }
       return nums1;
   }
   ```


### python版

1. 给定一个整数数组和一个目标值，找出数组中和为目标值的**两个**数。你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。**示例:**

   ```
   给定 nums = [2, 7, 11, 15], target = 9
   因为 nums[0] + nums[1] = 2 + 7 = 9
   所以返回 [0, 1]
   ```


