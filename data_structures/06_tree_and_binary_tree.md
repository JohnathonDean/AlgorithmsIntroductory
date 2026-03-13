# 树与二叉树

## 本章目标

- 理解树的层级结构
- 掌握二叉树的基本遍历
- 建立递归处理树问题的基本思路

## 知识要点

- 树是非线性结构
- 二叉树每个节点最多有两个孩子
- 树问题和递归密切相关
- 层序遍历通常依赖队列

## 主要内容

### 1. 树的基本概念

树中的节点按照层级组织，常见概念包括：

- 根节点
- 父节点
- 子节点
- 叶子节点
- 深度和高度

### 2. 二叉树遍历

二叉树最基础也最重要的内容是遍历：

- 前序遍历
- 中序遍历
- 后序遍历
- 层序遍历

### 3. 递归处理

树的很多问题都可以拆成左右子树的子问题。只要明确递归终止条件和返回结果，很多看起来复杂的题目都会变得清晰。

## 示例代码

```cpp
#include <iostream>
#include <queue>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

void preorder(TreeNode* root) {
    if (root == nullptr) {
        return;
    }
    cout << root->val << " ";
    preorder(root->left);
    preorder(root->right);
}

void inorder(TreeNode* root) {
    if (root == nullptr) {
        return;
    }
    inorder(root->left);
    cout << root->val << " ";
    inorder(root->right);
}

void levelorder(TreeNode* root) {
    if (root == nullptr) {
        return;
    }
    queue<TreeNode*> q;
    q.push(root);
    while (!q.empty()) {
        TreeNode* node = q.front();
        q.pop();
        cout << node->val << " ";
        if (node->left != nullptr) {
            q.push(node->left);
        }
        if (node->right != nullptr) {
            q.push(node->right);
        }
    }
}

int tree_height(TreeNode* root) {
    if (root == nullptr) {
        return 0;
    }
    int left_height = tree_height(root->left);
    int right_height = tree_height(root->right);
    return max(left_height, right_height) + 1;
}

int main() {
    TreeNode* root = new TreeNode(1);
    root->left = new TreeNode(2);
    root->right = new TreeNode(3);
    root->left->left = new TreeNode(4);
    root->left->right = new TreeNode(5);

    preorder(root);
    cout << '\n';
    inorder(root);
    cout << '\n';
    levelorder(root);
    cout << '\n';
    cout << tree_height(root) << '\n';
    return 0;
}
```

## 注意事项

- 递归终止条件要写明确
- 遍历顺序不能混淆
- 层序遍历通常需要先判断根节点是否为空

## 本章小结

树与二叉树的学习重点是遍历和递归。只要能把树看成由多个子树构成的层级结构，很多问题都会变得更容易分解和求解。
