
## #Day24/100 12-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 1304. Find N Unique Integers Sum up to Zero <font color="Red"> -Unwatched </font>
#### Example 1:

Input: n = 5\
Output: [-7,-1,1,3,4]\
Explanation: These arrays also are accepted [-5,-1,1,2,3] , [-3,-1,2,-2,4].

#### Example 2:
Input: n = 3\
Output: [-1,0,1]
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    vector<int> sumZero(int n) {

      vector<int> answer(n);
      int x;
        if(n%2==0){
         x=n/2;
        answer[n-1]=0;
        }
        else
         x=(n-1)/2; 
        for(int i=1;i<=x;i++){    
              answer[i-1]=-1*i;          
              answer[i-1+x]=i;
        }
      return answer; 
    }
};
```
