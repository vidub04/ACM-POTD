# Day 9 - POTD

## Problem Description
Given head, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Return true if there is a cycle in the linked list. Otherwise, return false.


## Approach

**Floyd’s Cycle Detection Algorithm (Tortoise and Hare)**

This approach is used to detect a cycle in a singly linked list efficiently without extra space. It uses two pointers: a slow pointer that moves one step at a time and a fast pointer that moves two steps at a time.

Both pointers start at the head of the list. As the traversal proceeds, if the list contains a cycle, the fast pointer will eventually catch up to the slow pointer, meaning they will point to the same node at some point. This happens because the fast pointer moves at a higher speed and loops around the cycle.

If there is no cycle, the fast pointer will reach the end of the list (i.e., become `nullptr`), and the loop terminates.

This algorithm runs in O(n) time and uses O(1) extra space, making it optimal for cycle detection in linked lists.

 

## 👨‍💻 Code

class Solution {
public:
    bool hasCycle(ListNode *head) {
        if (head == nullptr) return false;
        ListNode* slow = head;
        ListNode* fast = head;
        while (fast != nullptr && fast->next != nullptr) {
            slow = slow->next;
            fast = fast->next->next;
            if (slow == fast) {
                return true;
            }
        }
        return false;
    }
};
## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD9.jpg)
