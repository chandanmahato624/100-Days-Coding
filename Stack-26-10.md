
## #Day7/100 26-10-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 71. Simplify Path

#### Example 1:

Input: path = "/home/"\
Output: "/home"\
Explanation: Note that there is no trailing slash after the last directory name.

#### Example 2:
Input: path = "/../"\
Output: "/"\
Explanation: Going one level up from the root directory is a no-op, as the root level is the highest level you can go.

```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    string simplifyPath(string path) {
        stack<string> st;
        string res;
        for(int i=0; i<path.size(); ++i){
            if(path[i]=='/')
            continue;
            string temp;
            while(i<path.size() && path[i]!='/'){
                temp+=path[i];
                ++i;
            }
            if(temp=="."){
                continue;
            }else if(temp==".."){
                if(!st.empty()){
                    st.pop();
                }
            }else{
                st.push(temp);
            }
        }
        while(!st.empty()){
            res="/"+st.top()+res;
            st.pop();
        }
        if(res.size()==0){
            return "/";
        }
        return res;
    }
};
```

### 155. Min Stack  <font color="Red"> -Try Without Stack </font>
#### Example 1:

Input: ["MinStack","push","push","push","getMin","pop","top","getMin"]\
[[],[-2],[0],[-3],[],[],[],[]]\

Output:
[null,null,null,null,-3,null,0,-2]

Explanation:
MinStack minStack = new MinStack();\
minStack.push(-2);\
minStack.push(0);\
minStack.push(-3);\
minStack.getMin(); // return -3\
minStack.pop();\
minStack.top();    // return 0\
minStack.getMin(); // return -2


```bash
  Medium level coding questions
```
### Code

```javascript
class MinStack {
public:
    stack<int> st1, st2;
    MinStack() {

    } 
    void push(int val) {
        st1.push(val);
        if(!st2.empty()){
            val = min(val, st2.top());
        }
        st2.push(val);
    }
    void pop() {
        st1.pop();
        st2.pop();
    }
    int top() {
      return st1.top(); 
    }  
    int getMin() {
     return st2.top();   
    }
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(val);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->getMin();
 */
```

### 67. Add Binary<font color="Red"> -Unwatched </font>

#### Example 1:

Input: a = "11", b = "1"\
Output: "100"

#### Example 2:
Input: a = "1010", b = "1011"\
Output: "10101"
 
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    string addBinary(string a, string b) {
        string ans;
    int carry = 0;
    int i = a.length() - 1;
    int j = b.length() - 1;

    while (i >= 0 || j >= 0 || carry) {
      if (i >= 0)
        carry += a[i--] - '0';
      if (j >= 0)
        carry += b[j--] - '0';
      ans += carry % 2 + '0';
      carry /= 2;
    }

    reverse(begin(ans), end(ans));
    return ans;
    }
};
```