# 并查集

## 本章目标

- 理解并查集的用途
- 掌握 `find` 与 `union`
- 理解路径压缩和按秩合并

## 知识要点

- 并查集适合处理连通性问题
- 每个集合有一个代表元
- 路径压缩能提高查找效率

## 主要内容

### 1. 并查集的作用

并查集适合回答这样的问题：

- 两个元素是否属于同一集合
- 两个集合如何快速合并

### 2. 两个核心操作

- `find(x)`：查找根节点
- `union(x, y)`：合并两个集合

### 3. 优化方法

路径压缩和按秩合并都是为了减少树高，从而提高后续操作效率。

## 示例代码

```cpp
#include <iostream>
#include <vector>
using namespace std;

class UnionFind {
public:
    explicit UnionFind(int n) : parent(n), rank_(n, 0) {
        for (int i = 0; i < n; ++i) {
            parent[i] = i;
        }
    }

    int find(int x) {
        if (parent[x] != x) {
            parent[x] = find(parent[x]);
        }
        return parent[x];
    }

    void unite(int x, int y) {
        int root_x = find(x);
        int root_y = find(y);
        if (root_x == root_y) {
            return;
        }
        if (rank_[root_x] < rank_[root_y]) {
            parent[root_x] = root_y;
        } else if (rank_[root_x] > rank_[root_y]) {
            parent[root_y] = root_x;
        } else {
            parent[root_y] = root_x;
            ++rank_[root_x];
        }
    }

    bool connected(int x, int y) {
        return find(x) == find(y);
    }

private:
    vector<int> parent;
    vector<int> rank_;
};

int main() {
    UnionFind uf(5);
    uf.unite(0, 1);
    uf.unite(1, 2);
    cout << uf.connected(0, 2) << '\n';
    cout << uf.connected(0, 3) << '\n';
    return 0;
}
```

## 注意事项

- 初始化时每个元素都应自成一个集合
- 合并前先查找根节点

## 本章小结

并查集是一种高效维护集合关系的结构。只要理解根节点、集合合并和路径压缩，就能处理大量基础连通性问题。
