---
title: Linked List 연습문제 5
date: 2024-12-26 14:47:00 +0900
categories: [Question]  
tags:  [ C, C++, DataStructure]
---

Linked List에 익숙해지기 위한 연습문제 5 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/LinkedList5.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
struct NODE
{
    char word;
    NODE* left;
    NODE* right;
    
    NODE(char _word)
    {
        word = _word;
    }
};

void Print(std::string str);

NODE* head = nullptr;

int main()
{
    NODE node('A');
    head = &node;
    head->left = new NODE('B');
    head->right = new NODE('C');
    head->left->left = new NODE('D');
    head->left->right = new NODE('E');
    
    std::string str;
    std::cin >> str;
    
    Print(str);
    
    // 입력
    // HLL

    // 결과
    // D

    return 0;
}

void Print(std::string str)
{
    if (str == "H")
        std::cout << head->word;
    else if (str == "HL")
        std::cout << head->left->word;
    else if (str == "HR")
        std::cout << head->right->word;
    else if (str == "HLL")
        std::cout << head->left->left->word;
    else if (str == "HLR")
        std::cout << head->left->right->word;
}
```

---------------------------------------

# 후기

node의 이동을 이해하기 위한 문제인거같다
