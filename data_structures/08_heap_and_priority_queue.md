# 堆与优先队列

## 本章目标

- 理解堆的局部有序性质
- 掌握大根堆与小根堆
- 熟悉 `priority_queue` 的基本用法

## 知识要点

- 堆适合动态维护最值
- 堆通常用数组实现
- 堆顶元素最特殊，但整体并非完全有序

## 主要内容

### 1. 堆的基本性质

堆分为大根堆和小根堆。无论哪一种，都只保证父节点和孩子节点之间满足一定大小关系，而不保证整个序列完全有序。

### 2. 堆的应用场景

当题目要求：

- 动态插入元素
- 快速得到当前最大值或最小值

这类场景通常都适合使用堆。

### 3. 优先队列

在 C++ 中，优先队列是堆的常用接口：

- 默认是大根堆
- 加比较器可以实现小根堆

## 示例代码

```cpp
#include <functional>
#include <iostream>
#include <queue>
#include <vector>
using namespace std;

int main() {
    priority_queue<int> max_heap;
    max_heap.push(3);
    max_heap.push(10);
    max_heap.push(5);
    cout << max_heap.top() << '\n';
    max_heap.pop();
    cout << max_heap.top() << '\n';

    priority_queue<int, vector<int>, greater<int>> min_heap;
    min_heap.push(3);
    min_heap.push(10);
    min_heap.push(5);
    cout << min_heap.top() << '\n';
    return 0;
}
```

## 注意事项

- 不要把堆理解成完全排序结构
- 小根堆的比较器容易写错

## 本章小结

堆和优先队列的本质是快速维护当前最值。理解“局部有序”这一点后，就能准确区分堆和普通排序结构的差别。
