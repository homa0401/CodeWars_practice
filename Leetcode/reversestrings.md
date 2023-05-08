# [Reverse String](https://leetcode.com/explore/learn/card/recursion-i/250/principle-of-recursion/1440/)

Write a function that reverses a string. The input string is given as an array of characters s.

You must do this by modifying the input array in-place with O(1) extra memory.

 

Example 1:

```
Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]
```

Example 2:

```
Input: s = ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
```


Constraints:

```
1 <= s.length <= 105
s[i] is a printable ascii character.
```


```javascript
function reverseString(s) {
  let first = 0;
  let last = s.length - 1;

  while (first <= last) {
    let temp = s[first];
    s[first] = s[last];
    s[last] = temp;
    first++;
    last--;
  }
  return s
}
```
