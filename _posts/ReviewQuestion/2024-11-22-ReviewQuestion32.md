---
title: 기본기 복습문제32.
date: 2024-11-22 22:46:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 32번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/Reviewstring5.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int main()
{
    int arrays[5][5] =
    {
        { 4, 5, 4, 5, 4 },
        { 8, 9, 8, 9, 8 },
        { 1, 2, 1, 2, 1 },
        { 4, 5, 4, 5, 4 },
        { 6, 7, 6, 7, 6 }
    };

    for(int i = 0; i < 5; i++)
    {
        int x, y;
        std::cin >> y >> x;

        arrays[y][x]++;
        if(arrays[y][x] >= 10)
            arrays[y][x] = 0;
    }

    for(int i = 0 ; i < 5; i++)
    {
        for(int j = 0; j < 5; j++)
            std::cout << arrays[i][j];

        std::cout << std::endl;
    }

    // 입력 
    // 0 0
    // 0 0
    // 0 0
    // 1 1
    // 1 2

    // 결과
    // 75454
    // 80998
    // 12121
    // 45454
    // 67676

    return 0;
}
```
---------------------------------------

# 후기

노가다 문제

