---
title: 기본기 복습문제29.
date: 2024-11-22 22:21:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 29번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/Reviewstring2.png){:w = "700" h = "400"}

---------------------------------------

# 풀이
포인터 복습문제.

```c++

int main()
{
    int a, b;
    char c, d;
     
    std::cin >> a >> b; 
    std::cin >> c >> d;
     
    int* ptrA = &a;
    int* ptrB = &b;
    char* ptrC = &c;
    char* ptrD = &d;
     
    for (int i = 0; i < *ptrA; i++)
        std::cout << *ptrC;
     
    std::cout << std::endl;
    
    for (int i = 0; i < *ptrB; i++)
        std::cout << *ptrD;
     
    std::cout << std::endl;
     
    // 입력 : 3 5 C T

    // 결과
    // CCC
    // TTTTT

    return 0;
}
```
---------------------------------------

# 후기

돌아온 포인터..

