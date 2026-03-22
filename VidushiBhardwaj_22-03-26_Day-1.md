# Day 1 - POTD

## Problem Description
You are given a sorted array. Remove duplicate values so that each number appears only once.
Keep the order the same
Do it in-place (don’t use extra space)
Return the number of unique elements (k)
First k elements of the array should be the unique value


## Approach

This solution uses the two-pointer technique to remove duplicates from a sorted array in-place.

* Pointer `i` keeps track of the index of the last unique element.
* Pointer `j` traverses the array from left to right.
* Whenever a new unique element is found (i.e., `nums[i] != nums[j]`), it is placed at position `i+1`, and `i` is incremented.
* A counter is maintained to count the number of unique elements.

## Complexity

* Time Complexity: O(n), array is traversed once.
* Space Complexity: O(1), since no extra space is used.


## 👨‍💻 Code

class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int l=nums.size();
        if(l==1){
            return 1;
        }
        if(l==0){
            return 0;
        }
        int j=1;
        int i=0;
        int ctr=1;
        while(j<l){
            if(nums[i]!=nums[j]){
                nums[i+1]=nums[j];
                i++;
                ctr++;
            }
            j++;
        }
        return ctr;
    }
};

## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD1.jpg)

