# 数据结构学习总览（C++）

## 简介

这份文档用于介绍 C++ 数据结构各章节的主要内容，并帮助建立整套资料的整体结构。具体示例代码模板已经拆分到对应章节文件中，可以配合本页一起阅读。

阅读本页时，可以先把它当作整套资料的提纲页：先建立整体认识，再按章节深入学习具体实现与题型。

当前这份总览页按照新的主线目录组织内容，重点突出线性结构、树结构、图结构与查找结构之间的递进关系。

开始学习前，建议先具备以下基础：

- C++ 基础语法：变量、循环、函数、结构体、类
- 指针与引用
- 动态内存：`new`、`delete`
- STL 基础：`vector`、`string`、`pair`
- 复杂度分析：`O(1)`、`O(log n)`、`O(n)`、`O(n log n)`、`O(n^2)`


参考书：

- 《数据结构、算法与应用 C++ 语言描述》
- *Data Structures, Algorithms, and Applications in C++, Second Edition*


## 主目录

1. 线性表：数组描述 - [01_arrays_and_sequence_list.md](./01_arrays_and_sequence_list.md)
2. 线性表：链表描述 - [02_linked_list.md](./02_linked_list.md)
3. 矩阵 - [03_matrix.md](./03_matrix.md)
4. 栈 - [04_stack.md](./04_stack.md)
5. 队列 - [05_queue.md](./05_queue.md)
6. 跳表和散列 - [06_skip_list_and_hashing.md](./06_skip_list_and_hashing.md)
7. 树与二叉树 - [07_tree_and_binary_tree.md](./07_tree_and_binary_tree.md)
8. 堆与优先队列 - [08_heap_and_priority_queue.md](./08_heap_and_priority_queue.md)
9. 二叉搜索树 - [09_binary_search_tree.md](./09_binary_search_tree.md)
10. 平衡搜索树 - [10_balanced_search_tree.md](./10_balanced_search_tree.md)
11. 并查集 - [11_union_find.md](./11_union_find.md)
12. 图 - [12_graph.md](./12_graph.md)

## 章节总览

### 1. 线性表：数组描述

章节文件: [01_arrays_and_sequence_list.md](./01_arrays_and_sequence_list.md)

主要内容：

- `linearList` 抽象数据类型
- 数组描述与顺序存储思想
- `arrayList` 的核心状态与基本操作
- 顺序表的搬移代价与扩容问题

### 2. 线性表：链表描述

章节文件: [02_linked_list.md](./02_linked_list.md)

主要内容：

- 线性表的链式表示
- `chainNode` 与 `chain` 的基本结构
- 单链表的基本操作与前驱节点处理
- 头结点、循环链表、双向链表
- 链式表示与数组描述的对照

### 3. 矩阵

章节文件: [03_matrix.md](./03_matrix.md)

主要内容：

- 矩阵的二维逻辑结构
- 二维数组与地址映射
- 稠密矩阵与稀疏矩阵
- 特殊矩阵的压缩存储思想

### 4. 栈

章节文件: [04_stack.md](./04_stack.md)

主要内容：

- 栈作为受限线性表的定义
- 顺序栈与链式栈
- 栈的基本操作与边界问题
- 栈在递归、匹配和回溯中的作用

### 5. 队列

章节文件: [05_queue.md](./05_queue.md)

主要内容：

- 队列作为受限线性表的定义
- 顺序队列与循环队列
- 链式队列与双端队列
- 队列在层序处理和 BFS 中的作用

### 6. 跳表和散列

章节文件: [06_skip_list_and_hashing.md](./06_skip_list_and_hashing.md)

主要内容：

- 查找效率提升的基本思路
- 跳表的多层有序索引结构
- 散列的映射定位思想
- 有序查找与映射查找的对照

### 7. 树与二叉树

章节文件: [07_tree_and_binary_tree.md](./07_tree_and_binary_tree.md)

主要内容：

- 树的基本概念
- 二叉树的节点结构与表示
- 前序、中序、后序、层序遍历
- 递归处理树问题的基本思路

### 8. 堆与优先队列

章节文件: [08_heap_and_priority_queue.md](./08_heap_and_priority_queue.md)

主要内容：

- 优先队列的抽象定义
- 大根堆与小根堆
- 堆的顺序表示与局部有序性
- 堆与优先队列的关系

### 9. 二叉搜索树

章节文件: [09_binary_search_tree.md](./09_binary_search_tree.md)

主要内容：

- BST 的有序性
- 查找、插入、删除的基本思路
- 中序遍历与有序序列的关系
- BST 的效率与树高问题

### 10. 平衡搜索树

章节文件: [10_balanced_search_tree.md](./10_balanced_search_tree.md)

主要内容：

- 搜索树退化与平衡需求
- AVL 树与红黑树
- 旋转与局部调整思想
- 平衡搜索树与普通 BST 的关系

### 11. 并查集

章节文件: [11_union_find.md](./11_union_find.md)

主要内容：

- 不相交集合的基本问题
- `find` 与 `union`
- 父节点表示法
- 路径压缩与按秩合并

### 12. 图

章节文件: [12_graph.md](./12_graph.md)

主要内容：

- 图的基本概念
- 邻接矩阵与邻接表
- DFS 与 BFS
- 访问标记与图遍历
- 图与树的关系

## 总结

学习顺序可以概括为：先掌握线性结构及其受限形式，再进入树与搜索结构，最后学习集合关系和图这种更一般的连接结构。

- 基础结构部分：数组、链表、矩阵
- 受限线性结构部分：栈、队列
- 树与搜索结构部分：跳表和散列、树与二叉树、堆、二叉搜索树、平衡搜索树
- 集合与关系结构部分：并查集、图
