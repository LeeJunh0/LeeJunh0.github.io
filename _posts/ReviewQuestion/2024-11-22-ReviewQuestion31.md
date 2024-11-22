---
title: 기본기 복습문제31.
date: 2024-11-22 22:37:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 31번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/Reviewstring4.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int main()
{
    int arrays[5][5] = {0, };
    int input;
    std::cin >> input;

    for(int i = 0; i < 5; i++)
        arrays[0][i] = input;
    for(int i = 0; i < 5; i++)
        arrays[i][0] = input;
    for(int i = 0; i < 5; i++)
        arrays[i][4] = input;
    for(int i = 0; i < 5; i++)
        arrays[4][i] = input;

    for(int i = 0; i < 5; i++)
    {
        for(int j = 0; j < 5; j++)
        {
            if(arrays[i][j] > 0)
                std::cout << arrays[i][j];
            else
                std::cout << "_";
        }

        std::cout << std::endl;
    }

    // 입력 : 7

    // 결과
    // 77777
    // 7___7
    // 7___7
    // 7___7
    // 77777

    return 0;
}
```
---------------------------------------

# 후기

숫자 채우기를 빙자한 노가다 문제

