# [RansomNote](https://leetcode.com/problems/ransom-note/)

Given two strings ransomNote and magazine, return true if ransomNote can be constructed by using the letters from magazine and false otherwise.

Each letter in magazine can only be used once in ransomNote.

 

Example 1:

```
Input: ransomNote = "a", magazine = "b"
Output: false
```

Example 2:

```
Input: ransomNote = "aa", magazine = "ab"
Output: false
```

Example 3:

```
Input: ransomNote = "aa", magazine = "aab"
Output: true
```

Constraints:

```
1 <= ransomNote.length, magazine.length <= 105
ransomNote and magazine consist of lowercase English letters.
```

```javascript
function canConstruct(ransomNote, magazine) {
    const charCount = {};
    
    // Store the count of each character in the magazine string
    for (let i = 0; i < magazine.length; i++) {
        const char = magazine.charAt(i);
        charCount[char] = charCount[char] ? charCount[char] + 1 : 1;
    }
    
    // Check if all the characters in ransomNote are present in magazine
    for (let i = 0; i < ransomNote.length; i++) {
        const char = ransomNote.charAt(i);
        if (!charCount[char]) {
            return false;
        }
        charCount[char]--;
    }
    
    return true;
}
```

