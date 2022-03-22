# Leetcode

### question 1

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to `target`*.

You may assume that each input would have ***exactly\* one solution**, and you may not use the *same* element twice.

**Example 1:**

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**

```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

**Example 3:**

```
Input: nums = [3,3], target = 6
Output: [0,1]
```

 

**Constraints:**

- `2 <= nums.length <= 104`
- `-109 <= nums[i] <= 109`
- `-109 <= target <= 109`
- **Only one valid answer exists.**

## ==answer==

Solution #1

``` python
class solution:
    def twosum(self, nums:list[int],target:int):
        for i in nums:  # i = 2
            j = target - i  # j = 9-2 = 7
            start_num = nums.index(i)  # start_num= 0
            next_index = start_num.index + 1  # next_num = 1
            temp_num = nums[next_index:]  # temp_num =[7,11,15]
            if j in temp_num:  # j=7 in temp_num
                return (nums.index(i), next_index + temp_num.index(j))  # return(index(0),1+0)
```

Solution #2

```python
class solution:
    def twosum(self, nums:list[int],target:int):
        dict = {}

        for i in range(len(nums)):    #i in range(0,1,2,3)
            if target - nums[i] not in dict:  #if 9 - 2 != num in dict
                dict[nums[i]] = i   #dict[
            else:
                return[dict[target-nums[i]],i]
```



## question 2

You are given two **non-empty** linked lists representing two non-negative integers. The digits are stored in **reverse order**, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

 

**Example 1:**

![img](Day 8.assets/addtwonumber1.jpg)

```
Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.
```

**Example 2:**

```
Input: l1 = [0], l2 = [0]
Output: [0]
```

**Example 3:**

```
Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]
```

### ==answer==

