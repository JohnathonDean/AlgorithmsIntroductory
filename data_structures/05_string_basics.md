# 字符串与基础应用

## 本章目标

- 熟悉 C++ `string` 的基础操作
- 理解常见字符串问题的处理方法
- 能完成回文、查找、统计等基础题型

## 知识要点

- 字符串本质上是字符序列
- 常见操作包括遍历、截取、查找和比较
- 字符串问题常与双指针、哈希表结合

## 主要内容

### 1. 字符串对象

C++ 的 `string` 提供了比字符数组更方便的操作接口，适合大部分日常使用和算法练习。

### 2. 常见处理方法

字符串题通常围绕以下内容展开：

- 回文判断
- 子串查找
- 字符统计
- 模拟处理

### 3. 与其他数据结构的联系

很多字符串题并不是独立的，它们常和以下方法结合：

- 双指针
- 哈希计数
- 栈处理括号或表达式

## 示例代码

```cpp
#include <iostream>
#include <string>
using namespace std;

bool is_palindrome(const string& s) {
    int left = 0;
    int right = static_cast<int>(s.size()) - 1;
    while (left < right) {
        if (s[left] != s[right]) {
            return false;
        }
        ++left;
        --right;
    }
    return true;
}

int main() {
    string s = "level";
    cout << is_palindrome(s) << '\n';
    cout << s.substr(1, 3) << '\n';
    cout << s.find("eve") << '\n';
    return 0;
}
```

## 注意事项

- `substr()` 的参数含义要分清
- 字符和字符串不要混淆

## 本章小结

字符串这一章的核心是掌握常用接口和基本处理思路。只要能把字符串看作可遍历、可统计的序列，后续复杂题型就更容易理解。
