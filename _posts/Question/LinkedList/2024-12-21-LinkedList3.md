---
title: Linked List 연습문제 3
date: 2024-12-25 15:54:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 3 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList3.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
struct BBQ
{
    int a = 0;
    int b = 0;
}

int main()
{
    BBQ node;
    BBQ* heap = new BBQ();
    heap = &node;

    std::cin >> node.a >> node.b;
    std::cout << heap->a + 5, " " << heap->b + 5;

    // 입력
    // 1 4

    // 결과
    // 6 9

    return 0;
}
```

---------------------------------------

# 후기

배우면서 처음으로 동적할당이라는것을 사용한 문제였다.
