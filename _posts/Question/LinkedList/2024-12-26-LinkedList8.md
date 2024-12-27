---
title: Linked List 연습문제 8
date: 2024-12-26 16:08:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 8 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList8.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
#include <iostream>

struct Node
{
    std::string name;
    Node* love1 = NULL;
    Node* love2 = NULL;
    
    Node(std::string _name)
    {
        name = _name;
    }
};

Node* head = nullptr;

int main()
{
    Node temp("boss");
    head = &temp;
    head->love1 = new Node("wife");
    head->love2 = new Node("son");
    head->love1->love1 = head;
    head->love1->love2 = head->love2;
    head->love2->love1 = new Node("girlfriend");
    head->love2->love2 = new Node("boyfriend");
    head->love2->love1->love1 = head->love2;
    head->love2->love1->love2 = head->love2->love2;
    head->love2->love2->love1 = head->love2->love1;
    
    std::cout << head->love2->love1->name << " " << head->love2->love2->name;
    
    // 결과
    // girlfriend boyfriend

    return 0;
}

```

---------------------------------------

# 후기

복잡한 노드구성을 읽을줄알고 어떻게 연결하는지 이해하는 문제인거같다.
