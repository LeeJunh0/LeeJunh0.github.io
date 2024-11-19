---
title: 기본기 복습문제12.
date: 2024-11-19 16:39:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 12번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray4.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

for문 심화문제다.

```c++


int main()
{
    int a, b, c;
    std::cin >> a >> b >> c;

    int arrays[3][4];
    arrays[0][0] = a;
    arrays[1][0] = b;
    arrays[2][0] = c;

    for(int i = 0; i < 3; i++)
    {
        for(int j = 1; j < 4; j++)
            arrays[i][j] = arrays[i][j - 1] + 1;
    }

    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 4; j++)
            std::cout << arrays[i][j] << " ";

        std::cout << std::endl;
    }

    // 입력 : 1 11 7
    // 결과
    // 1 2 3 4
    // 11 12 13 14
    // 7 8 9 10

    return 0;
}
```
---------------------------------------

# 후기

.

