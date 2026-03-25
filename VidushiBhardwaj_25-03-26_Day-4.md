# Day 4 - POTD

## Problem Description
Missing Number problem

Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array


## Approach

This approach uses the mathematical sum formula to find the missing number efficiently.

It calculates:

The actual sum of elements present in the array (sum)
The expected sum of numbers from 0 to n (finsum)

Since exactly one number is missing, the difference between the expected sum and the actual sum (finsum - sum) gives the missing value directly.

This method avoids sorting or extra data structures, making it:

Time Complexity: O(n)
Space Complexity: O(1)



## 👨‍💻 Code

class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int sum=0;
        int finsum=0;
        for(int i=0;i<nums.size();i++){
            sum+=nums[i];
        }
        for(int i=0;i<=nums.size();i++){
            finsum+=i;
        }
        return finsum-sum;  
    }
};
## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD4.jpg)
