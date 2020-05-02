## 1. Two Sum

*Easy*

![image-20200502174708318](G:\LeetCode\docs\Top-100-Liked-Questions\Top-100-Liked-Questions.assets\image-20200502174708318.png)

Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.

You may assume that each input would have **exactly** one solution, and you may not use the *same* element twice.

**Example:**

```
Given nums = [2, 7, 11, 15], target = 9,
Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

---

### Solution 1: Brute Force

```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> res;
        for(int i = 0; i < nums.size(); i++){
            for(int j = 0; j < nums.size(); j++){
                if(i == j)continue;
                if(nums[i] + nums[j] == target){
                    res.push_back(i);
                    res.push_back(j);
                    return res;
                }
            }
        }
        return res;
    }
};
```

!>  重要内容

- Time complexity: $O(n^2)$

- Space complexity: $O(1)$

  

  

  