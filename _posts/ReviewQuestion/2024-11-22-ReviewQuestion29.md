---
title: 기본기 복습문제28.
date: 2024-11-22 21:43:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 28번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/Reviewstring1.png){:w = "700" h = "400"}

---------------------------------------

# 풀이
다시.. 구조체 문제.

```c++
struct NODE
{
    int x;
    int y;
};

int main()
{
    NODE ta, tb;
     
    std::cin >> ta.x >> tb.x;
    ta.y = ta.x + 5;
    tb.y = tb.x - 5;
     
    std::cout << "ta.x = " << ta.x << std::endl;
    std::cout << "ta.b = " << ta.y << std::endl;
    std::cout << "tb.x = " << tb.x << std::endl;
    std::cout << "tb.y = " << tb.y << std::endl;

    // 입력 : 3 5

    // 결과
    // ta.x = 3
    // ta.b = 8
    // tb.x = 5
    // tb.y = 0

    return 0;
}
```
---------------------------------------

# 후기

구조체 복습문제 같다.

