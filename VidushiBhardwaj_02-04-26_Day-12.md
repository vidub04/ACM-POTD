# Day 12 - POTD

## Problem Description
Given the head of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list sorted as well.


## Approach

This approach removes duplicates from a **sorted singly linked list** by using two pointers: `prev` and `curr`.

* `prev` points to the last node that is confirmed to be unique (or retained).
* `curr` is used to traverse the list and check for duplicates.

The algorithm works as follows:

1. Start with `prev` at the head and `curr` at the next node.
2. Traverse the list while `curr` is not `nullptr`.
3. If `prev->val == curr->val`, a duplicate is found:

   * Skip the duplicate node by updating `prev->next = curr->next`.
   * Disconnect `curr` and move it forward.
4. If values are different:

   * Move both `prev` and `curr` one step forward.
5. Continue until the end of the list.

Since the list is sorted, duplicates always appear consecutively, which allows this single-pass comparison.

**Time Complexity:** O(n), as the list is traversed once.
**Space Complexity:** O(1), as no extra space is used.



## 👨‍💻 Code

/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        if (head == nullptr) {
            return head;
        }
        if (head->next == nullptr) {
            return head;
        }
        ListNode* curr = head->next;
        ListNode* prev = head;
        while (curr != nullptr) {
            if (prev->val == curr->val) {
                prev->next = curr->next;
                curr->next = nullptr;
                curr = prev->next;
                if (curr != nullptr && prev->val != curr->val) {
                    prev = curr;
                    curr = curr->next;
                }
            } else {
                prev = curr;
                curr = curr->next;
            }
        }
        return head;
    }
};

## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD12.jpg)
