---
title: Linked List 연습문제 9
date: 2025-01-04 02:26:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 9 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList9.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
struct Node
{
    int data;
    Node* next;

    Node(int data) : data(data)
    {}
};

void AddNode(int data);

Node* head = nullptr;
Node* tail = nullptr;

int main()
{
    int input;
    std::cin >> input;
    for(int i = 1; i <= 4; i++)
        AddNode(i * input);

    while(head != nullptr)
    {
        std::cout << head->data << " ";
        head = head->next;
    }
}

void AddNode(int data)
{
    if(head == nullptr)
    {
        Node* temp = new Node(data);
        temp->next = nullptr;
        head = temp;
        tail = head;
    }
    else
    {
        Node* temp = new Node(data);
        temp->next = nullptr;
        tail->next = temp;
        tail = tail->next;
    }
}
```

---------------------------------------

# 후기

이제부터는 링크드리스트는 물론이고 스택과 큐에 대한 문제도 나올꺼다.

이때까지 배운 개념들, 지식들을 잘 숙지 하고있는지 확인하는 문제같다.
