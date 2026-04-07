# Day 17 - POTD

## Problem Description
The next greater element of some element x in an array is the first greater element that is to the right of x in the same array.

You are given two distinct 0-indexed integer arrays nums1 and nums2, where nums1 is a subset of nums2.

For each 0 <= i < nums1.length, find the index j such that nums1[i] == nums2[j] and determine the next greater element of nums2[j] in nums2. If there is no next greater element, then the answer for this query is -1.

Return an array ans of length nums1.length such that ans[i] is the next greater element as described above.



## Approach

Uses two pointers starting at the heads of both linked lists
Each pointer moves one step at a time through its list
When a pointer reaches the end, it switches to the head of the other list
This makes both pointers travel equal total distance (lengthA + lengthB)
If an intersection exists, both pointers meet at the intersecting node
If no intersection exists, both pointers become null at the same time
Time complexity is linear, O(n + m)
Space complexity is constant, O(1)



## 👨‍💻 Code

/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */

 //not solved
 
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode *temp=headA;
        ListNode* temp2=headB;
        while(headA!=headB){
            if(headA==headB){
                return headA;
            }else if(headA==nullptr){
                headA=temp2;
            }else if(headB==nullptr){
                headB=temp;
            }else{
                headA=headA->next;
                headB=headB->next;
            }
        }
        
        return headA;
        
    }
};
## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD17.jpg)
