---
title: Linked List 연습문제 1
date: 2024-12-21 00:27:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 1 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList1.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
struct NODE
{
    int x;
    NODE* next;
};

int main()
{
    NODE a;
    NODE b;
    NODE c;
    
    a.x = 3;
    b.x = 4;
    c.x = 5;
    a.next = &b;
    b.next = &c;
    
    return 0;
}
```

---------------------------------------

# 후기

아주아주 간단하게 모양만 갖춘 LinkedList다

