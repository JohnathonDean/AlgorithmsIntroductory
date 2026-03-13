# 栈

## 本章目标

- 理解栈的后进先出特点
- 掌握栈的基本操作
- 能用栈解决括号匹配等基础问题

## 知识要点

- 栈是一种受限线性结构
- 数据的插入和删除都在同一端进行
- 栈适合处理最近相关的问题

## 主要内容

### 1. 栈的基本概念

栈的典型特征是后进先出，也就是最后进入栈的元素最先离开。常见操作包括：

- 入栈
- 出栈
- 查看栈顶

### 2. 栈的应用场景

在很多问题中，当前元素需要和“最近出现但还未处理完的元素”建立关系，这类问题通常适合使用栈。例如：

- 括号匹配
- 表达式求值
- 单调栈

### 3. C++ 中的栈

标准库提供了 `stack` 容器，可以直接使用。

## 示例代码

```cpp
#include <iostream>
#include <stack>
#include <string>
using namespace std;

bool is_valid_parentheses(const string& s) {
    stack<char> st;
    for (char ch : s) {
        if (ch == '(' || ch == '[' || ch == '{') {
            st.push(ch);
        } else {
            if (st.empty()) {
                return false;
            }
            char top = st.top();
            st.pop();
            if ((ch == ')' && top != '(') ||
                (ch == ']' && top != '[') ||
                (ch == '}' && top != '{')) {
                return false;
            }
        }
    }
    return st.empty();
}

int main() {
    cout << is_valid_parentheses("()[]{}") << '\n';
    cout << is_valid_parentheses("([)]") << '\n';
    return 0;
}
```

## 注意事项

- 出栈或取栈顶前先判断是否为空
- 不要只记接口，要理解栈的使用条件

## 本章小结

栈结构本身并不复杂，真正重要的是识别哪些问题适合用栈处理。理解后进先出的处理顺序，是掌握这一章的关键。
