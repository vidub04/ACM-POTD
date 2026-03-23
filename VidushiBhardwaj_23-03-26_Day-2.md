# Day 2 - POTD

## Problem Description
Two Sum Problem

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.


## Approach

### Approach: Hash Map (Two-Pass Method)

The solution uses a hash map to efficiently find two numbers in the array whose sum equals the given target.

First, all elements of the array are stored in an unordered map where each element is mapped to its index. This allows constant-time lookup for any value.

Next, the array is traversed again. For each element, the required complement is calculated as:

complement = target − current element

The algorithm then checks whether this complement exists in the hash map. If it exists, it means a pair has been found whose sum equals the target.

A condition is added to ensure that the same element is not used twice by verifying that the index of the complement is different from the current index.

Once such a pair is found, their indices are stored and returned as the result.


###Complexity

Time Complexity: O(n), since the array is traversed twice.
Space Complexity: O(n), due to the extra space used by the hash map.



## 👨‍💻 Code

class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {

        vector<int> v;

        unordered_map<int, int> s;
        for (int i = 0; i < nums.size(); i++) {
            s[nums[i]] = i;
        }

        for (int i = 0; i < nums.size(); i++) {
            int t = target - nums[i];
            if (s.find(t) != s.end()) {

                if (s[t] != i) {
                    v.push_back(s[t]);
                    v.push_back(i);
                    break;
                }
            }
        }
        return v;
    }
};

## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD2.jpg)
