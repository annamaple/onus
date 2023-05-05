---
title: "Morris遍历"
layout: "morris" # is necessary
# url: "/archive"
# description: "Description for Search"
summary: "Morris遍历代码模板"
placeholder: "placeholder text in search input box"
date: 2023-05-05T10:56:37+08:00
draft: false
---

# Morris遍历

```java
public void morris(TreeNode head) {
    TreeNode cur = head;
    while (cur != null) {
        TreeNode mostRight = cur.left;
        if (mostRight != null) {
            while (mostRight.right != null && mostRight.right != cur) {
                mostRight = mostRight.right;
            }
            if(mostRight.right == null) {
                mostRight.right = cur;
                cur = cur.left;
                continue;
            } else {
                mostRight.right = null;
            }
        }
        cur = cur.right;
    }
}

