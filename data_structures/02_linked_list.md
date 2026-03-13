# 链表

## 本章目标

- 理解链式存储的基本思想
- 掌握单链表的基本操作
- 理解链表与数组在存储和操作上的差异
- 能手写反转链表、删除节点等基础模板

## 知识要点

- 链表节点通过指针连接
- 链表不要求内存连续
- 插入和删除操作灵活
- 访问某个位置通常需要遍历

## 主要内容

### 1. 链式存储

链表中的每个节点除了保存数据之外，还会保存一个指向下一个节点的指针。借助这个指针，多个节点被串联起来，形成线性结构。

这种方式与数组最大的区别在于：

- 数组依赖连续内存
- 链表依赖节点之间的指针关系

### 2. 单链表的基本操作

学习单链表时，需要重点掌握：

- 头插法
- 尾插法
- 删除指定值节点
- 遍历输出
- 链表反转

### 3. 链表的优缺点

链表的优点：

- 插入、删除灵活
- 不要求连续内存

链表的缺点：

- 随机访问能力弱
- 指针操作更容易出错

## 示例代码

```cpp
#include <iostream>
using namespace std;

struct ListNode {
    int val;
    ListNode* next;
    ListNode(int x) : val(x), next(nullptr) {}
};

class LinkedList {
public:
    LinkedList() : head(nullptr) {}

    void push_front(int value) {
        ListNode* node = new ListNode(value);
        node->next = head;
        head = node;
    }

    void push_back(int value) {
        ListNode* node = new ListNode(value);
        if (head == nullptr) {
            head = node;
            return;
        }
        ListNode* cur = head;
        while (cur->next != nullptr) {
            cur = cur->next;
        }
        cur->next = node;
    }

    void erase_value(int value) {
        ListNode dummy(0);
        dummy.next = head;
        ListNode* prev = &dummy;
        while (prev->next != nullptr) {
            if (prev->next->val == value) {
                ListNode* to_delete = prev->next;
                prev->next = to_delete->next;
                delete to_delete;
                break;
            }
            prev = prev->next;
        }
        head = dummy.next;
    }

    void reverse() {
        ListNode* prev = nullptr;
        ListNode* cur = head;
        while (cur != nullptr) {
            ListNode* next_node = cur->next;
            cur->next = prev;
            prev = cur;
            cur = next_node;
        }
        head = prev;
    }

    void print() const {
        ListNode* cur = head;
        while (cur != nullptr) {
            cout << cur->val << " ";
            cur = cur->next;
        }
        cout << '\n';
    }

private:
    ListNode* head;
};

int main() {
    LinkedList list;
    list.push_back(1);
    list.push_back(2);
    list.push_front(0);
    list.print();

    list.erase_value(1);
    list.print();

    list.reverse();
    list.print();
    return 0;
}
```

## 注意事项

- 修改指针前先保存后继节点
- 删除节点时注意释放内存
- 空链表和单节点链表要单独考虑

## 本章小结

链表的关键在于通过指针维护节点关系。它牺牲了随机访问能力，换来了更灵活的插入和删除操作，是理解动态结构的重要基础。
