试题链接：[41. 包含min函数的栈 - AcWing题库](https://www.acwing.com/problem/content/description/90/)

## 方法一：辅助栈

- 思路：用一个辅助栈专门用来存放当前栈中的最小值，每次新增一个元素就那它和辅助栈栈顶的元素相比较，取最小的一个放在栈顶，取最小值的时候直接从辅助栈获取即可。
- 时间复杂度：O(1)
- 空间复杂度：O(1)

```cpp
class MinStack {
public:
    MinStack() {
        
    }
    
    void push(int x) {
        if (stk.empty()) {
            stk.push(x);
            min_stk.push(x);
        } else {
            stk.push(x);
            min_stk.push(min(x, min_stk.top()));
        }
    }
    
    void pop() {
        stk.pop();
        min_stk.pop();
    }
    
    int top() {
        return stk.top();
    }
    
    int getMin() {
        return min_stk.top();
    }

private:
    stack<int> stk;
    stack<int> min_stk;
};
```
