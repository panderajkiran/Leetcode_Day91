# Leetcode_Day91
# Day 91 – First Unique Character in a String

**LeetCode Problem:** [387. First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)

**Difficulty:** Easy  
**Topic:** String, Array, Frequency Counting  
**Language:** Java

## Problem Statement

Given a string `s`, find the first character that appears only once and return its index.

If no such character exists, return `-1`.

## Approach: Frequency Array

I used an integer array of size 26 to store the frequency of each lowercase English letter.

1. Create an array `freq[26]` initialized with zeros.
2. Traverse the string and count the frequency of each character.
3. Traverse the string again from left to right.
4. Check whether the current character has a frequency of exactly 1.
5. Return its index. If no unique character is found, return `-1`.

This approach helps identify the first non-repeating character efficiently.

## Java Solution

```java
class Solution {
    public int firstUniqChar(String s) {
        int[] freq = new int[26];

        for(int i = 0; i < s.length(); i++) {
            freq[s.charAt(i) - 'a']++;
        }

        for(int i = 0; i < s.length(); i++) {
            if(freq[s.charAt(i) - 'a'] == 1) {
                return i;
            }
        }

        return -1;
    }
}
```

## Complexity Analysis

- **Time Complexity:** O(n) – We traverse the string twice.
- **Space Complexity:** O(1) – We use a fixed-size array of 26 elements.

## What I Learned

- How to use a frequency array to count character occurrences.
- How character indexing works using `s.charAt(i) - 'a'`.
- Why traversing the string again helps preserve the original order.
- How a simple array can solve a string problem efficiently.

## Takeaway

Sometimes, the simplest approach is also the most efficient. Counting first and checking later makes finding the first unique character straightforward.

**Day 91 completed! Another problem solved, another concept added to my learning journey.**
