# 数组与顺序表

## 本章目标

- 理解数组的连续存储特点
- 掌握顺序表的基本操作
- 熟悉 C++ 中原生数组和 `vector` 的基础使用
- 能分析数组插入、删除、查找的复杂度

## 知识要点

- 数组是一种连续存储的线性结构
- 顺序表可以看作对数组的进一步抽象
- 数组适合随机访问，不适合中间频繁插入和删除
- `vector` 是 C++ 中最常用的动态顺序表

## 主要内容

### 1. 数组的基本特点

数组中的元素在内存中按顺序连续存放。由于存储位置连续，因此可以根据首地址和下标直接定位任意一个元素。

这带来两个直接结果：

- 按下标访问元素速度快
- 数组长度固定时管理简单

### 2. 顺序表的含义

顺序表不是新的底层结构，而是建立在数组之上的线性表组织方式。它强调“逻辑上的线性关系”和“基于位置的操作”。

在实际编程中，顺序表常常通过动态数组实现。在 C++ 里，`vector` 就是最典型的工具。

### 3. 插入与删除

如果在数组中间插入一个新元素，后面的元素通常都要向后移动。如果删除中间元素，后面的元素又要整体前移。因此：

- 中间插入通常为 `O(n)`
- 中间删除通常为 `O(n)`

这也是数组和链表最重要的差异之一。

### 4. C++ 中的使用方式

原生数组适合固定长度场景，例如：

```cpp
int a[5] = {1, 2, 3, 4, 5};
```

如果希望长度可以动态变化，更推荐使用 `vector`。

## 示例代码

```cpp
#include <iostream>
#include <vector>
using namespace std;

class SequenceList {
public:
    void insert(int pos, int value) {
        if (pos < 0 || pos > static_cast<int>(data.size())) {
            return;
        }
        data.insert(data.begin() + pos, value);
    }

    void erase(int pos) {
        if (pos < 0 || pos >= static_cast<int>(data.size())) {
            return;
        }
        data.erase(data.begin() + pos);
    }

    int find(int value) const {
        for (int i = 0; i < static_cast<int>(data.size()); ++i) {
            if (data[i] == value) {
                return i;
            }
        }
        return -1;
    }

    void print() const {
        for (int x : data) {
            cout << x << " ";
        }
        cout << '\n';
    }

private:
    vector<int> data;
};

int main() {
    SequenceList seq;
    seq.insert(0, 10);
    seq.insert(1, 20);
    seq.insert(1, 15);
    seq.print();

    seq.erase(0);
    seq.print();

    cout << seq.find(20) << '\n';
    return 0;
}
```

## 注意事项

- 不要忽视下标越界问题
- 不要把 `size()` 和 `capacity()` 混为一谈
- 中间插入删除时要意识到元素搬移成本

## 本章小结

数组与顺序表的核心在于连续存储和随机访问。理解这一点后，就能自然看出它在访问效率上的优势，以及在中间修改操作上的局限性。
