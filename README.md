<h1 align="center">100 days of DSA</h1>
<h2 align="center">DSA is Fun! Do it everyday 💯💯</h2>

###start-solving-you-will-fall-in-❤️❤️

1. **[Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) ?**

```javascript
function Palindrome(s) {
  const string = s.replace(/[^A-Z0-9]/gi, "").toLowerCase();
  const reverseString = string.split("").reverse().join("");

  if (string !== reverseString) return false;

  return true;
}

console.log(Palindrome("")); //true
console.log(Palindrome("race a car")); //false
console.log(Palindrome("A man, a plan, a canal: Panama")); //true
console.log(Palindrome("#% A %&  man, a plan, a canal: &&Pan&^&ama")); // true
```

```javascript
function Palindrome(s) {
  const string = s.replace(/[^A-Z0-9]/gi, "").toLowerCase();
  const length = string.length;

  for (let i = 0; i < Math.floor(string.length / 2); i++) {
    if (string[i] != string[length - 1 - i]) {
      return false;
    }
  }
  return true;
}
```

2. **[Valid Anagram](https://leetcode.com/problems/valid-anagram/) ?**

```javascript
function Anagram(s, t) {
  if (s.length !== t.length) {
    return false;
  }

  const charCount = {};

  for (let char of s) {
    if (charCount[char]) {
      charCount[char] += 1;
    } else {
      charCount[char] = 1;
    }
  }

  for (let char of t) {
    if (!charCount[char]) {
      return false;
    }
    charCount[char]--;
  }

  return true;
}

console.log(Anagram("anagram", "nagaram")); //true
console.log(Anagram("rat", "car")); // false
console.log(Anagram("aacc", "ccac")); //false
```

3. **[Valid Parentheses](https://leetcode.com/problems/valid-parentheses/) ?**

```javascript
function validParentheses(str) {
  let length;

  do {
    length = str.length;
    str = str.replace("()", "").replace("{}", "").replace("[]", "");
  } while (length !== str.length);
  return str.length === 0;
}

console.log(validParentheses("()")); //true
console.log(validParentheses("()[]{}")); //true
console.log(validParentheses("(]")); //false
```

```javascript
function validParentheses(s) {
  let obj = { "(": ")", "{": "}", "[": "]" };
  let arr = [];
  for (let char of s) {
    if (obj[char]) arr.push(char);
    else if (obj[arr.pop()] !== char) return false;
  }
  return arr.length == 0;
}
console.log(validParentheses("()")); //true
console.log(validParentheses("()[]{}")); //true
console.log(validParentheses("(]")); //false
```

4. **[Array Reversal with constant space complexity](https://leetcode.com/problems/reverse-string/) ?**

```javascript
function reverseString(s) {
  let start = 0;
  let end = s.length - 1;
  while (start <= end) {
    [s[start], s[end]] = [s[end], s[start]];
    start++;
    end--;
  }
  return s;
}

console.log(reverseString(["h", "e", "l", "l", "o"]));
```

5. **[Longest common prefix](https://leetcode.com/problems/longest-common-prefix/) ?**

```javascript
function longestCommonPrefix(arr) {
  if (!arr.length) return "";
  let longestPrefix = "";
  for (let i = 0; i < arr[0].length; i++) {
    if (arr[0] == "") return "";
    if (arr.every((str) => str[i] === arr[0][i])) {
      longestPrefix += arr[0][i];
    } else break;
  }
  return longestPrefix;
}

console.log(longestCommonPrefix(["string", "strings", "tring"]));
```

**[⬆ Back to Top](#start-solving-you-will-fall-in-❤️❤️)**

---
