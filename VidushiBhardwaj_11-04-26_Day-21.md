# Day 17 - POTD

## Problem Description
Given a string s of lower and upper case English letters.

A good string is a string which doesn't have two adjacent characters s[i] and s[i + 1] where:

0 <= i <= s.length - 2
s[i] is a lower-case letter and s[i + 1] is the same letter but in upper-case or vice-versa.
To make the string good, you can choose two adjacent characters that make the string bad and remove them. You can keep doing this until the string becomes good.

Return the string after making it good. The answer is guaranteed to be unique under the given constraints.

Notice that an empty string is also good.



## Approach

Use stack
For each char: if stack not empty and stack top is same letter but different case → pop
Else push current char
Return stack as string
Core Idea: Stack removes bad pairs immediately as they form.
Time: O(n) | Space: O(n)




## 👨‍💻 Code

string makeGood(string s) {
    string st;
    for (char c : s) {
        if (!st.empty()&&abs(st.back()-c)==32) st.pop_back();
        else st+=c;
    }
    return st;
}
## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD21.jpg)
