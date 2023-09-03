# leet-day51
---

# Group Anagrams

## Problem Description

Given an array of strings `strs`, group the anagrams together. An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

## Example

**Input:**

```cpp
vector<string> strs = ["eat", "tea", "tan", "ate", "nat", "bat"];
```

**Output:**

```cpp
vector<vector<string>> result = [["bat"], ["nat", "tan"], ["ate", "eat", "tea"]];
```

## Approach

We can use an unordered map to group anagrams efficiently. The idea is to sort each word in the input vector and use the sorted word as a key in the map. Words that result in the same sorted word when sorted are anagrams of each other and will be grouped together.

1. Initialize an unordered map `mp` where the key is a sorted version of each word in the input vector, and the value is a vector of words that match the key when sorted.
2. Iterate through each word in the input vector.
3. For each word, create a copy named `sortedWord` and sort it.
4. Use this sorted `sortedWord` as the key in the unordered map `mp` and add the original word to the corresponding vector.
5. After iterating through all the words, we have an unordered map where each key corresponds to a sorted version of one or more words.
6. Iterate through the map and push each vector of anagrams into the `ans` vector, effectively grouping all anagrams together.
7. Return the `ans` vector containing grouped anagrams.

## Complexity Analysis

- Time complexity: O(N * K * log(K)), where N is the number of strings in `strs`, and K is the maximum length of a string in the vector. Sorting each string takes O(K * log(K)) time, and you do this for each of the N strings.
- Space complexity: O(N * K), as we store all the words in the map.

---

This README provides an overview of the problem, the approach used to solve it, and the complexity analysis. You can include this information in your project's documentation to help others understand your solution.
