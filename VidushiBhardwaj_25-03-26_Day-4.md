# Day 4 - POTD

## Problem Description
Missing Number problem

Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array


## Approach

This approach solves the problem by first sorting the array and then checking for the first index where the value does not match the index.

After sorting, the array should ideally contain numbers from `0` to `n` in order. The algorithm iterates through the array and compares each element `nums[i]` with its index `i`. If a mismatch is found (`nums[i] != i`), that index is the missing number. A variable `a` is used to store this result.

Additionally, a counter `ctr` is used to check if the value `n` appears in the array. If no mismatch is found (`a == -1`) and `n` is not present (`ctr == 0`), then the missing number must be `n`, since all values from `0` to `n-1` are present.

Time complexity is dominated by sorting, which is `O(n log n)`, and the space complexity is `O(1)` (ignoring the sorting implementation details).



###Complexity

Time Complexity: O(n log n), since the array sorted.
Space Complexity: O(1).



## 👨‍💻 Code

class Solution {
public:
    int missingNumber(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        int n=nums.size();
        int a=-1;
        int ctr=0;
        for(int i=0;i<n;i++){
            if(nums[i]!=i){
                a=i;
                break;
            }
            if(nums[i]==n){
                ctr++;
            }
        }
        if(a==-1&&ctr==0){
            return n;
        }else{
            return a;
        }   
    }
};
## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD4.jpg)
