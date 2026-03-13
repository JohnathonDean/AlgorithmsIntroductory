# 数据结构学习总览（C++）

## 简介

这份文档用于介绍 C++ 数据结构各章节的主要内容，并概括每一章的学习重点。具体示例代码模板已经拆分到对应章节文件中，可以配合本页一起阅读。

## 学习前置知识

在正式开始前，建议先具备以下基础：

- C++ 基础语法：变量、循环、函数、结构体、类
- 指针与引用
- 动态内存：`new`、`delete`
- STL 基础：`vector`、`string`、`pair`
- 复杂度分析：`O(1)`、`O(log n)`、`O(n)`、`O(n log n)`、`O(n^2)`

## 主目录

1. 数组与顺序表: [01_arrays_and_sequence_list.md](./01_arrays_and_sequence_list.md)
2. 链表: [02_linked_list.md](./02_linked_list.md)
3. 栈: [03_stack.md](./03_stack.md)
4. 队列: [04_queue.md](./04_queue.md)
5. 字符串与基础应用: [05_string_basics.md](./05_string_basics.md)
6. 树与二叉树: [06_tree_and_binary_tree.md](./06_tree_and_binary_tree.md)
7. 二叉搜索树: [07_binary_search_tree.md](./07_binary_search_tree.md)
8. 堆与优先队列: [08_heap_and_priority_queue.md](./08_heap_and_priority_queue.md)
9. 哈希表: [09_hash_table.md](./09_hash_table.md)
10. 图: [10_graph.md](./10_graph.md)
11. 并查集: [11_union_find.md](./11_union_find.md)
12. 进阶结构: [12_advanced_structures.md](./12_advanced_structures.md)

## 章节总览

### 1. 数组与顺序表

章节文件: [01_arrays_and_sequence_list.md](./01_arrays_and_sequence_list.md)

主要内容：

- 数组的连续存储特性
- 顺序表的基本操作
- 原生数组与 `vector` 的使用
- 插入、删除、查找的复杂度分析

学习重点：

- 理解为什么数组支持随机访问
- 明确中间插入和删除为什么代价较高
- 熟悉 `vector` 的常见操作和使用边界

### 2. 链表

章节文件: [02_linked_list.md](./02_linked_list.md)

主要内容：

- 单链表、双链表、循环链表
- 链表节点与指针连接关系
- 插入、删除、反转、遍历
- 快慢指针基础应用

学习重点：

- 理解链式存储和顺序存储的区别
- 掌握指针修改顺序
- 能独立写出反转链表和删除节点的模板

### 3. 栈

章节文件: [03_stack.md](./03_stack.md)

主要内容：

- 后进先出结构
- 栈的基本操作
- 栈在括号匹配、表达式处理中的应用
- 单调栈入门

学习重点：

- 明确栈只处理栈顶元素的特点
- 理解“最近相关元素”类问题为什么适合用栈
- 熟悉 `stack` 的基本接口

### 4. 队列

章节文件: [04_queue.md](./04_queue.md)

主要内容：

- 先进先出结构
- 普通队列、循环队列、双端队列
- 队列在层序遍历和 BFS 中的使用
- 滑动窗口相关应用

学习重点：

- 理解队列和栈的差异
- 掌握 BFS 的基本写法
- 理解双端队列在区间问题中的作用

### 5. 字符串与基础应用

章节文件: [05_string_basics.md](./05_string_basics.md)

主要内容：

- `string` 的基本操作
- 字符串遍历、截取、查找
- 回文判断
- 字符统计和模拟类题目

学习重点：

- 熟悉 C++ 字符串常用接口
- 理解字符串题与数组、哈希表之间的联系
- 能处理基础字符串模拟问题

### 6. 树与二叉树

章节文件: [06_tree_and_binary_tree.md](./06_tree_and_binary_tree.md)

主要内容：

- 树的基本概念
- 二叉树节点定义
- 前序、中序、后序、层序遍历
- 树高、节点数等基础递归问题

学习重点：

- 建立递归处理树问题的思维方式
- 熟练掌握四种遍历
- 理解树的层级结构和递归终止条件

### 7. 二叉搜索树

章节文件: [07_binary_search_tree.md](./07_binary_search_tree.md)

主要内容：

- BST 的有序性
- 查找、插入、删除
- 中序遍历与有序序列的关系
- BST 退化问题

学习重点：

- 理解左小右大的性质
- 会写基础查找和插入模板
- 重点掌握删除节点的分类讨论

### 8. 堆与优先队列

章节文件: [08_heap_and_priority_queue.md](./08_heap_and_priority_queue.md)

主要内容：

- 大根堆与小根堆
- 堆的局部有序性
- `priority_queue` 的使用
- Top K 与动态最值维护

学习重点：

- 理解堆不是完全排序结构
- 熟悉大根堆和小根堆的区别
- 学会在“动态维护最值”场景中使用堆

### 9. 哈希表

章节文件: [09_hash_table.md](./09_hash_table.md)

主要内容：

- 哈希映射思想
- `unordered_map` 和 `unordered_set`
- 计数、去重、快速查找
- 哈希冲突的基本认识

学习重点：

- 理解哈希表为什么查询快
- 区分 `map` 和 `unordered_map`
- 掌握基础计数和查重问题的写法

### 10. 图

章节文件: [10_graph.md](./10_graph.md)

主要内容：

- 图的基本概念
- 邻接表和邻接矩阵
- DFS 与 BFS
- 连通性和遍历问题

学习重点：

- 掌握邻接表建图
- 理解 `visited` 标记的重要性
- 能写出 DFS、BFS 的通用模板

### 11. 并查集

章节文件: [11_union_find.md](./11_union_find.md)

主要内容：

- 集合合并与查询
- `find` 与 `union`
- 路径压缩
- 连通性问题应用

学习重点：

- 理解并查集处理“是否属于同一集合”的问题
- 掌握路径压缩优化
- 能用并查集解决基础连通性题目

### 12. 进阶结构

章节文件: [12_advanced_structures.md](./12_advanced_structures.md)

主要内容：

- AVL 树
- 红黑树
- 树状数组
- 线段树
- Trie 字典树

学习重点：

- 先建立用途认知，再逐步深入实现细节
- 理解区间查询、平衡维护、前缀匹配等典型问题
- 知道每种结构适合解决哪一类题目

## 使用建议

阅读本页时，重点先看每章的“主要内容”和“学习重点”；需要代码模板时，再跳转到对应章节文件。这样可以先建立整体认识，再进入具体实现。
