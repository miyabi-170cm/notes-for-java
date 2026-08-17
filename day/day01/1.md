## [1.两数之和](https://leetcode.cn/problems/two-sum/description/?envType=study-plan-v2&envId=top-100-liked)

**难度**：简单　**状态**：✅ 已AC

### 题目
给定一个整数数组 `nums` 和一个整数目标值 `target`，找出和为目标值的那两个整数，并返回它们的下标。


### 解题思路
哈希表遍历，找到target-x是否存在，不存在加入，存在返回

### 解法代码 (Java)
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer,Integer> map=new HashMap<>();
        for(int i=0;i<nums.length;i++)
        {
            int y=target-nums[i];
            if(map.containsKey(y))
            {
                return new int[]{i,map.get(y)};
            }
            else
            {
                map.put(nums[i],i);
            }
        }
        return new int[]{-1,-1};
    }
}
```

### 复杂度
- 时间：O(n)　空间：O(n)

### 思考
- 边判断边存，出现结果直接退出，节省开销

- map里只有前i个元素，避免同一个下标 i 被用两次




---
