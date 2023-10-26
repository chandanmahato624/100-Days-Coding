
## #Day5/100 24-10-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 14. Longest Common Prefix <font color="Red"> -Unwatched </font>

#### Example 1:

Input: strs = ["flower","flow","flight"]\
Output: "fl"

#### Example 2:
Input: strs = ["dog","racecar","car"]\
Output: ""\
Explanation: There is no common prefix among the input strings.

```bash
  Easy level coding questions
```


### JAVA-Code

```javascript
class Solution {
    public String longestCommonPrefix(String[] strs) {
        Arrays.sort(strs);
        String s1 = strs[0];
        String s2 = strs[strs.length-1];
        int idx = 0;
        while(idx < s1.length() && idx < s2.length()){
            if(s1.charAt(idx) == s2.charAt(idx)){
                idx++;
            } else {
                break;
            }
        }
        return s1.substring(0, idx);       
    }
}
```

### 392. Is Subsequence  <font color="Red"> -Unwatched </font>
#### Example 1:

Input: s = "abc", t = "ahbgdc"\
Output: true

#### Example 2:
Input: s = "axc", t = "ahbgdc"\
Output: false
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    bool isSubsequence(string s, string t) {
       if(s==t)
        return true;
        int j=0;
        for(int i=0;i<t.length();i++){
            if(s[j]==t[i])
                j++;
            if(j==s.length())
               return true;
        }
        return false; 
    }
};
```

### 242. Valid Anagram <font color="Red"> -Unwatched </font>

#### Example 1:

Input: s = "anagram", t = "nagaram"\
Output: true

#### Example 2:
Input: s = "rat", t = "car"\
Output: false
 
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    bool isAnagram(string s, string t) {
        sort(s.begin(), s.end());
        sort(t.begin(), t.end());
        return s == t;
    }
};
```