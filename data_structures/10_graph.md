# 图

## 本章目标

- 理解图的基本概念和存储方式
- 掌握邻接表建图
- 能写出 DFS 和 BFS 的基础模板

## 知识要点

- 图可以描述复杂连接关系
- 邻接表是常用存储方式
- DFS 与 BFS 是图遍历基础
- `visited` 标记通常不可缺少

## 主要内容

### 1. 图的表示

图可以分为有向图和无向图，也可以分为带权图和无权图。常见存储方式有：

- 邻接矩阵
- 邻接表

### 2. 深度优先搜索与广度优先搜索

DFS 强调优先向深处搜索，BFS 强调逐层扩展。它们是图论中最基础的两种遍历方式。

### 3. 访问标记

由于图中可能存在环，如果不记录访问状态，就可能重复访问同一个节点，甚至陷入死循环。

## 示例代码

```cpp
#include <iostream>
#include <queue>
#include <vector>
using namespace std;

void dfs(int u, const vector<vector<int>>& graph, vector<int>& visited) {
    visited[u] = 1;
    cout << u << " ";
    for (int v : graph[u]) {
        if (!visited[v]) {
            dfs(v, graph, visited);
        }
    }
}

void bfs(int start, const vector<vector<int>>& graph) {
    vector<int> visited(graph.size(), 0);
    queue<int> q;
    q.push(start);
    visited[start] = 1;

    while (!q.empty()) {
        int u = q.front();
        q.pop();
        cout << u << " ";
        for (int v : graph[u]) {
            if (!visited[v]) {
                visited[v] = 1;
                q.push(v);
            }
        }
    }
}

int main() {
    vector<vector<int>> graph = {
        {1, 2},
        {0, 3},
        {0, 3},
        {1, 2}
    };

    vector<int> visited(graph.size(), 0);
    dfs(0, graph, visited);
    cout << '\n';
    bfs(0, graph);
    cout << '\n';
    return 0;
}
```

## 注意事项

- 建图时要看清题目是否有向
- BFS 和 DFS 都要重视访问标记

## 本章小结

图的学习重心是建图和遍历。掌握邻接表、DFS、BFS 之后，很多图论基础题都能顺利展开。
