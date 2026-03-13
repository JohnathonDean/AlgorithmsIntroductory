# 二叉搜索树

## 本章目标

- 理解 BST 的有序性质
- 掌握查找、插入和基础遍历
- 认识删除操作的分类处理思路

## 知识要点

- 左子树节点值小于根节点
- 右子树节点值大于根节点
- 中序遍历结果有序
- BST 最坏情况下可能退化

## 主要内容

### 1. 有序性

二叉搜索树最大的特点就是“左小右大”。正是因为这个性质，查找时不需要像普通二叉树一样遍历全部节点。

### 2. 查找与插入

查找和插入都依赖大小比较：

- 小于当前节点，走左子树
- 大于当前节点，走右子树

### 3. 删除思路

删除节点时需要分情况讨论：

- 叶子节点
- 只有一个孩子的节点
- 有两个孩子的节点

## 示例代码

```cpp
#include <iostream>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

TreeNode* insert_bst(TreeNode* root, int val) {
    if (root == nullptr) {
        return new TreeNode(val);
    }
    if (val < root->val) {
        root->left = insert_bst(root->left, val);
    } else if (val > root->val) {
        root->right = insert_bst(root->right, val);
    }
    return root;
}

bool search_bst(TreeNode* root, int target) {
    if (root == nullptr) {
        return false;
    }
    if (root->val == target) {
        return true;
    }
    if (target < root->val) {
        return search_bst(root->left, target);
    }
    return search_bst(root->right, target);
}

void inorder(TreeNode* root) {
    if (root == nullptr) {
        return;
    }
    inorder(root->left);
    cout << root->val << " ";
    inorder(root->right);
}

int main() {
    TreeNode* root = nullptr;
    root = insert_bst(root, 5);
    root = insert_bst(root, 3);
    root = insert_bst(root, 7);
    root = insert_bst(root, 4);

    inorder(root);
    cout << '\n';
    cout << search_bst(root, 4) << '\n';
    cout << search_bst(root, 6) << '\n';
    return 0;
}
```

## 注意事项

- 递归插入时注意接住返回值
- 删除节点时一定要分类讨论

## 本章小结

二叉搜索树在普通二叉树的基础上增加了有序性，因此查找效率更高。掌握这一性质，是继续学习平衡树等结构的前提。
