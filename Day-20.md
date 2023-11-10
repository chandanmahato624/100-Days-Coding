
## #Day20/100 08-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 476. Number Complement
#### Example 1:

Input: num = 5\
Output: 2\
Explanation: The binary representation of 5 is 101 (no leading zero bits), and its complement is 010. So you need to output 2.

#### Example 2:
Input: num = 1
Output: 0
Explanation: The binary representation of 1 is 1 (no leading zero bits), and its complement is 0. So you need to output 0.
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int findComplement(int num) {
        long k=1;
        while(k<=num){
            num^=k;
            k*=2;
        }
        return num;
    }
};
```
