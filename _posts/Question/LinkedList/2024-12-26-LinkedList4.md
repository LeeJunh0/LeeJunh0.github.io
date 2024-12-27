---
title: Linked List 연습문제 4
date: 2024-12-26 14:28:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 4 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList4.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
#include <iostream>

struct Node
{
    int n;
    Node* left = NULL;
    Node* right = NULL;
    
    Node(int num)
    {
        n = num;
    }
};

Node* head = nullptr;

int main()
{
    Node Node1(3);
    head = &Node1;
    
    head->left = new Node(7);
    head->right = new Node(6);
    head->right->left = new Node(2);
     
    return 0;
}

```

---------------------------------------

# 후기

그림처럼 head에 포인터연산자를 사용해서 왼쪽 오른쪽으로 이동하며 동적할당을

해주었다.
