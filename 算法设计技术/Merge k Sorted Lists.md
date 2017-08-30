### 问题
23.Merge k Sorted Lists

Merge k sorted linked lists and return it as one sorted list. Analyze and describe its complexity.

### 思路
归并排序思想：
1. 分解：先将k个链表分解为两个均等部分
2. 求解：分别递归合并左右两部分
3. 合并：将左右两部分的合并结果再合并到一个链表中


### 实现

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def mergeKLists(self, lists):
        """
        :type lists: List[ListNode]
        :rtype: ListNode
        """
        # 边界
        for i in xrange(len(lists)-1,-1,-1):
            if not lists[i]:
                del lists[i]
        n = len(lists)
        if not n:
            return None
        elif n == 1:
            return lists[0]
        
        # 分解
        mid = (n-1)/2
        # 求解
        left = self.mergeKLists(lists[:mid+1])
        right = self.mergeKLists(lists[mid+1:])
        # 合并 
        first = cur = ListNode(0)
        while left and right:
            if left.val < right.val:
                cur.next,left = left,left.next
            else:
                cur.next,right = right,right.next
            cur = cur.next
        cur.next = left or right
        
        return first.next
```

### 分析
- 时间复杂度： O(nlgn)
- 空间复杂度： O(lgn)