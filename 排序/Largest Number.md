### 问题
Given a list of non negative integers, arrange them such that they form the largest number.

For example, given [3, 30, 34, 5, 9], the largest formed number is 9534330.

Note: The result may be very large, so you need to return a string instead of an integer.

由给定非负整数列表，所能组合出的最大整数（返回一个字符串）

### 思路
对列表进行排序，如果str(x)+str(y) > str(y)+str(x)，则x应位于y前面，最后再将所有元素依次合并为字符串

### 实现

```python
def largestNumber(self, nums):
    nums.sort(cmp = lambda x,y:cmp(str(y)+str(x),str(x)+str(y)))
    return ''.join(str(x) for x in nums).lstrip('0') or '0'

#         for i in xrange(1,len(nums)):
#             j = i - 1
#             x = nums[i]
#             while str(x) + str(nums[j]) > str(nums[j]) + str(x) and j >= 0:
#                 nums[j+1] = nums[j]
#                 j -= 1
#             nums[j+1] = x
        
#         res = ''.join(str(x) for x in nums)
#         return res if int(res) else '0'
```

### 分析
- 时间复杂度：和具体所用排序方法有关，插入排序O(n2)
- 空间复杂度：插入排序O(1)