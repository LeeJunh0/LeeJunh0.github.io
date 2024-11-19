---
title: 기본기 복습문제14.
date: 2024-11-19 16:58:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 14번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray6.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

구조체 개념문제다.

```c++

struct BBQ
{
    int x;
    int data[3];
};

int main()
{
    BBQ g;
    std::cin >> g.x >> g.data[0] >> g.data[1] >> g.data[2];

    int sum = 0;
    for(int i = 0; i < sizeof(g.data) / sizeof(int); i++)
        sum += g.data[i];

    std::cout << sum << " " << g.x;

    // 입력 : 3 5 4 1
    // 결과
    // 10 3

    return 0;
}

```
---------------------------------------

# 후기

구조체에 배열을 정의해 그 배열안에 값을 넣는걸 목표로 하는거같다.

