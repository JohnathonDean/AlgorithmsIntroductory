# 队列

## 本章目标

- 理解队列的先进先出特点
- 掌握队列和双端队列的基本使用
- 能用队列完成基础 BFS 遍历

## 知识要点

- 队列是一种受限线性结构
- 插入和删除分别发生在两端
- 队列适合按进入顺序处理数据
- 双端队列可以从两端操作元素

## 主要内容

### 1. 队列的基本概念

队列的典型特征是先进先出。最早进入队列的元素最早被处理，这种结构很适合模拟排队过程。

### 2. 队列在遍历中的作用

队列在 BFS 中非常重要。因为 BFS 需要按层处理节点，而队列天然支持这种顺序。

### 3. 双端队列

双端队列既可以从头部操作，也可以从尾部操作，在滑动窗口等问题中很常见。

## 示例代码

```cpp
#include <iostream>
#include <queue>
#include <vector>
using namespace std;

vector<int> bfs_order(const vector<vector<int>>& graph, int start) {
    vector<int> order;
    vector<int> visited(graph.size(), 0);
    queue<int> q;
    q.push(start);
    visited[start] = 1;

    while (!q.empty()) {
        int u = q.front();
        q.pop();
        order.push_back(u);
        for (int v : graph[u]) {
            if (!visited[v]) {
                visited[v] = 1;
                q.push(v);
            }
        }
    }
    return order;
}

int main() {
    vector<vector<int>> graph = {
        {1, 2},
        {3},
        {3},
        {}
    };

    vector<int> order = bfs_order(graph, 0);
    for (int x : order) {
        cout << x << " ";
    }
    cout << '\n';
    return 0;
}
```

## 注意事项

- 访问标记通常要在入队时就设置
- 不要把栈和队列的处理顺序混淆

## 本章小结

队列的核心在于先进先出。它不仅是基础线性结构，也是理解层序遍历和 BFS 的关键工具。
