
## #Day19/100 07-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 338. Counting Bits <font color="Red"> -Unwatched </font>
#### Example 1:

Input: n = 2\
Output: [0,1,1]\
Explanation:\
0 --> 0\
1 --> 1\
2 --> 10

#### Example 2:
Input: n = 5\
Output: [0,1,1,2,1,2]\
Explanation:\
0 --> 0\
1 --> 1\
2 --> 10\
3 --> 11\
4 --> 100\
5 --> 101
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    vector<int> countBits(int n) {
        vector<int>v1;
        for(int i=0; i<=n; i++){
            int count = 0;
            int test = i;
            while(test>0){
                if(test%2==1){
                    count++;
                    test/=2;
                }else{
                    test/=2;
                }
            }
            v1.push_back(count);
        }
        return v1;
    }
};
```
