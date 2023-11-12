
## #Day20/100 08-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 2828. Check if a String Is an Acronym of Words <font color="Red"> -Unwatched </font>
#### Example 1:

Input: words = ["alice","bob","charlie"], s = "abc"\
Output: true\
Explanation: The first character in the words "alice", "bob", and "charlie" are 'a', 'b', and 'c', respectively. Hence, s = "abc" is the acronym.

#### Example 2:
Input: words = ["an","apple"], s = "a"\
Output: false\
Explanation: The first character in the words "an" and "apple" are 'a' and 'a', respectively. 
The acronym formed by concatenating these characters is "aa". 
Hence, s = "a" is not the acronym.
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    bool isAcronym(vector<string>& words, string s) {
       string str="";
        int n=words.size();
        for(int i=0;i<n;i++)
        {
            string str1=words[i];
            str.push_back(str1[0]);
        }
        if(s==str)
            return true;
        else
            return false; 
    }
};
```
