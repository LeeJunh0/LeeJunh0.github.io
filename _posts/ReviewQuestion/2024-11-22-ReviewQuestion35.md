---
title: 기본기 복습문제35.
date: 2024-11-22 23:22:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 35번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/Reviewstring8.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int main()
{
    int arrays[3][3];
    int input;
    std::cin >> input;
    
    for (int i = 0; i < 3; i++)
    {
        for (int j = 2 - i; j < 3; j++)
        {
            arrays[i][j] = input;
            input++;
        }
    }
    
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 3; j++)
        {
            if (0 < arrays[i][j])
            std::cout << arrays[i][j];
            else
            std::cout << 0;
        }
    
        std::cout << std::endl;
    }
    
    // 입력 : 3

    // 결과
    // 003
    // 045
    // 678

    return 0;
}

```
---------------------------------------

# 후기

후... 그래도 마지막 문제는 괜찮았다..
