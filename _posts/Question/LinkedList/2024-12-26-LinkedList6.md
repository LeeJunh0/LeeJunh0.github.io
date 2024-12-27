---
title: Linked List 연습문제 6
date: 2024-12-26 14:58:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 6 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList6.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
struct NODE
{
    int num;
    NODE* next = nullptr;
    
    NODE(int _num)
    {
    	num = _num;
    }
};

NODE* head = nullptr;

int main()
{
    NODE node(3);
    head = &node;
    head->next = new NODE(5);
    head->next->next = new NODE(4);
    head->next->next->next = new NODE(2);
    
    NODE* cur = head;
    while (cur != nullptr)
    {
        std::cout << cur->num << " ";
        cur = cur->next;
    }
    
    // 결과
    // 3 5 4 2

    return 0;
}
```

---------------------------------------

# 후기

처음노드에서 다음노드로 계속 이동하며 출력하면 되는 문제였다.
