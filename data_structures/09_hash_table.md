# 哈希表

## 本章目标

- 理解哈希表的映射思想
- 熟悉 `unordered_map` 和 `unordered_set`
- 能用哈希表完成计数、去重和查找

## 知识要点

- 哈希表追求平均意义下的快速查询
- 哈希冲突不可避免
- 哈希表通常不保证元素有序

## 主要内容

### 1. 哈希思想

哈希表通过某种映射规则，将键转换成存储位置，从而加快查找过程。它的核心目标是让查找尽量接近常数时间。

### 2. 常见用途

哈希表常用于：

- 频率统计
- 查重
- 判断某个元素是否存在

### 3. C++ 中的容器

最常用的是：

- `unordered_map`
- `unordered_set`

如果同时需要有序性，则通常考虑 `map` 或 `set`。

## 示例代码

```cpp
#include <iostream>
#include <string>
#include <unordered_map>
using namespace std;

int main() {
    unordered_map<string, int> freq;
    string text = "banana";

    for (char ch : text) {
        string key(1, ch);
        ++freq[key];
    }

    for (const auto& entry : freq) {
        cout << entry.first << ": " << entry.second << '\n';
    }

    cout << freq.count("a") << '\n';
    return 0;
}
```

## 注意事项

- 不要忽略哈希冲突这一事实
- `map` 和 `unordered_map` 的适用场景不同

## 本章小结

哈希表最大的优势是查询快。只要理解它适合计数、去重和存在性判断，就已经掌握了最常用的应用方式。
