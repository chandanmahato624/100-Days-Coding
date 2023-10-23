
## #Day4/100 23-10-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 125. Valid Palindrome

#### Example 1:

Input: s = "A man, a plan, a canal: Panama"\
Output: true\
Explanation: "amanaplanacanalpanama" is a palindrome.

#### Example 2:
Input: s = "race a car"\
Output: false\
Explanation: "raceacar" is not a palindrome.

```bash
  Easy level coding questions
```


### JAVA-Code

```javascript
class Solution {
    public boolean isPalindrome(String s) {
      if (s.isEmpty()) {
        	return true;
        }
        int start = 0;
        int last = s.length() - 1;
        while(start <= last) {
        	char currFirst = s.charAt(start);
        	char currLast = s.charAt(last);
        	if (!Character.isLetterOrDigit(currFirst )) {
        		start++;
        	} else if(!Character.isLetterOrDigit(currLast)) {
        		last--;
        	} else {
        		if (Character.toLowerCase(currFirst) != Character.toLowerCase(currLast)) {
        			return false;
        		}
        		start++;
        		last--;
        	}
        }
        return true;  
    }
}
```

### 58. Length of Last Word
#### Example 1:

Input: s = "Hello World"\
Output: 5\
Explanation: The last word is "World" with length 5.

#### Example 2:
IInput: s = "   fly me   to   the moon  "\
Output: 4\
Explanation: The last word is "moon" with length 4
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int lengthOfLastWord(string s) {
        int siz=s.size(),count=0,flag=0;
        for(int i=siz-1;i>=0;i--){
            if(s[i]==' '&&flag)break;
            if(s[i]!=' '){
                flag=1;
                count++;
            }
        }
        return count;
    }
};
```

### 28. Find the Index of the First Occurrence in a String

#### Example 1:

Input: haystack = "sadbutsad", needle = "sad"\
Output: 0\
Explanation: "sad" occurs at index 0 and 6.\
The first occurrence is at index 0, so we return 0.

#### Example 2:
Input: haystack = "leetcode", needle = "leeto"\
Output: -1\
Explanation: "leeto" did not occur in "leetcode", so we return -1.
 
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int strStr(string haystack, string needle) {
     return haystack.find(needle);
    }
};
```