---
title: 기본기 복습문제13.
date: 2024-11-19 16:48:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 13번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray5.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

전에 푼 해당 열 전체 값 바꾸기에서 해당 범위 전체 값 바꾸기로 진화했다.

```c++

int main()
{
    int arrays[6][3];
    
    int cur = 10;
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 6; j++)
        {
            arrays[j][i] = cur;
            cur++;
        }
    }
    
    int a, b;
    std::cin >> a >> b;
    
    for (int i = a; i <= b; i++)
    {
        for (int j = 0; j < 3; j++)
            arrays[i][j] = 7;
    }
    
    for (int i = 0; i < 6; i++)
    {
        for (int j = 0; j < 3; j++)
            std::cout << arrays[i][j] << " ";
    
        std::cout << std::endl;
    }

    // 입력 : 1 3
    // 결과
    // 10 16 22 
    // 7 7 7
    // 7 7 7
    // 7 7 7
    // 14 20 26
    // 15 21 27
    
    return 0;
}

```
---------------------------------------

# 후기

값 바꾸기 심화문제다 흥미로웠다

