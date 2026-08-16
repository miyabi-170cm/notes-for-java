# 01 数组 / 哈希表

> 专题进度：✅ 两数之和　⬜ 三数之和　⬜ ...

---

## 两数之和 (LeetCode 1)

**难度**：简单　**状态**：✅ 已AC

### 题目
给定一个整数数组 `nums` 和一个整数目标值 `target`，找出和为目标值的那两个整数，并返回它们的下标。

### 我的思路
1. 第一反应：暴力双重循环，每对都试一遍，O(n²)。
2. 优化：遍历时把「值 → 下标」存进 HashMap，同时检查 `target - nums[i]` 是否已经在 map 里，一次遍历搞定。

### 解法代码 (Java)
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int need = target - nums[i];
            if (map.containsKey(need)) {
                return new int[]{map.get(need), i};
            }
            map.put(nums[i], i);
        }
        return new int[0];
    }
}
```

### 复杂度
- 时间：O(n)　空间：O(n)

### 收获 & 坑
- 找「两数配对」的题，优先想哈希表
- 注意题目要求返回**下标**，不是值
- 新题直接复制上面这套标题结构，往下加章节即可

---
