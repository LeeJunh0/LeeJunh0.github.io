---
title: Linked List 연습문제 2
date: 2024-12-21 00:34:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 2 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList2.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
struct NODE
{
    int age;
    NODE* next1 = NULL;
    NODE* next2 = NULL;
    
    NODE(int _age)
    {
        age = _age;
    }
};

int main()
{
    NODE* head;
    
    NODE simson(20);
    NODE woman1(29);
    NODE woman2(30);
    NODE man1(25);
    NODE man2(40);
    NODE man3(38);
    
    head = &simson;
    simson.next1 = &woman1;
    simson.next2 = &woman2;
    woman1.next1 = &man1;
    woman1.next2 = &man2;
    woman2.next1 = woman1.next2;
    woman2.next2 = &man3;
    
    return 0;
}
```

---------------------------------------

# 후기

첫 node를 가지는 head가 simson을 가리키고있어

simson으로부터 연결되있는 모든 Node를 디버깅중에 확인할수있다.

