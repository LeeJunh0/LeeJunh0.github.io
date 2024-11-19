---
title: 기본기 복습문제11.
date: 2024-11-19 16:31:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 11번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray3.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

이건 구조체 개념문제다.

```c++

struct Fruit
{
    int price;
    int size;
};

int main()
{
    Fruit banana;
    Fruit apple;

    std::cin >> banana.size >> apple.size;

    banana.price = banana.size * 250;
    apple.price = apple.size * 500;

    std::cout << apple.price + banana.price << "원";

    // 입력 : 10 20
    // 결과
    // 12500원

    return 0;
}
```
---------------------------------------

# 후기

.

