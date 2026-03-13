# 进阶结构

## 本章目标

- 建立对常见进阶结构的整体认识
- 理解它们分别解决什么问题
- 为后续深入学习打下基础

## 知识要点

- 平衡树解决搜索树退化问题
- 树状数组和线段树处理区间问题
- Trie 适合前缀匹配

## 主要内容

### 1. 平衡树

AVL 树和红黑树都属于平衡搜索树。它们的核心任务是避免搜索树高度过高，从而保持较稳定的查找效率。

### 2. 树状数组

树状数组适合维护前缀和，并支持动态更新。它实现相对紧凑，是很常见的进阶入门结构。

### 3. 线段树

线段树适合处理区间查询和区间更新，是很多高阶题目的基础工具。

### 4. Trie 字典树

Trie 适合做前缀统计、字典检索等问题，尤其常见于字符串相关场景。

## 示例代码

```cpp
#include <iostream>
#include <vector>
using namespace std;

class FenwickTree {
public:
    explicit FenwickTree(int n) : tree(n + 1, 0) {}

    void add(int index, int delta) {
        for (int i = index; i < static_cast<int>(tree.size()); i += i & -i) {
            tree[i] += delta;
        }
    }

    int sum(int index) const {
        int result = 0;
        for (int i = index; i > 0; i -= i & -i) {
            result += tree[i];
        }
        return result;
    }

private:
    vector<int> tree;
};

int main() {
    FenwickTree bit(5);
    bit.add(1, 3);
    bit.add(2, 2);
    bit.add(5, 7);
    cout << bit.sum(2) << '\n';
    cout << bit.sum(5) << '\n';
    return 0;
}
```

## 注意事项

- 不要一开始就追求全部结构的完整实现
- 先分清每种结构的用途，再逐步深入

## 本章小结

进阶结构的学习重点在于“问题对应关系”。只要知道哪一类问题应该考虑哪一种结构，后续深入学习时就会更有方向感。
