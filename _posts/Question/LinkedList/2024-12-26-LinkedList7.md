---
title: Linked List 연습문제 7
date: 2024-12-26 15:25:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 7 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList7.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
struct NODE
{
    char word;
    NODE* next = nullptr;
    
    NODE(char _word)
    {
        word = _word;
    }
};

NODE* head = nullptr;

int main()
{
    char arr[5];
    for (int i = 0; i < 5; i++)
        std::cin >> arr[i];
    
    NODE* temp = new NODE(arr[0]);
    head = temp;
    head->next = new NODE(arr[1]);
    head->next->next = new NODE(arr[2]);
    head->next->next->next = new NODE(arr[3]);
    head->next->next->next->next = new NODE(arr[4]);
    
    NODE* cur = head;
    
    while (cur->next != nullptr)
        cur = cur->next;
    
    std::cout << cur->word;
    
    // 입력
    // Q T P K Q
    
    // 결과
    // Q

    return 0;
}
```

---------------------------------------

# 후기

head에서부터 쭉 노드를 동적으로 만들어 넣어주고

제일 마지막 노드의 값을 출력하는 문제였다.
