### 问题
Write an efficient algorithm that searches for a value in an m x n matrix. This matrix has the following properties:

Integers in each row are sorted in ascending from left to right.
Integers in each column are sorted in ascending from top to bottom.
For example,

Consider the following matrix:
```
[
  [1,   4,  7, 11, 15],
  [2,   5,  8, 12, 19],
  [3,   6,  9, 16, 22],
  [10, 13, 14, 17, 24],
  [18, 21, 23, 26, 30]
]
```
Given target = 5, return true.

Given target = 20, return false.

矩阵中每一行、每一列都递增，判断给定元素是否在矩阵中

### 思路
元素值是行列号的单调函数，考虑使用二分查找：
1. 首先以矩阵左下角为枢轴点和目标值进行比较
  1. 如果相等，则直接返回
  2. 如果目标值大于枢轴点，枢轴点列号+1
  3. 如果目标值小于枢轴点，枢轴点行号-1

### 实现

```python
class Solution(object):
    def searchMatrix(self, matrix, target):
        """
        :type matrix: List[List[int]]
        :type target: int
        :rtype: bool
        """
        if not matrix:return False
        r,c,n = len(matrix) - 1,0,len(matrix[0])
        
        while r >=0 and c < n:
            mid = matrix[r][c]
            if mid == target:
                return True
            elif mid > target:
                r -= 1
            else:
                c += 1
        return False

```

### 分析

- 时间复杂度：O(r+c)
- 空间复杂度：O(1)