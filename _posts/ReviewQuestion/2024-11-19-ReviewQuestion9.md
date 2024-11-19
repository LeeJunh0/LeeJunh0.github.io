---
title: 기본기 복습문제9.
date: 2024-11-19 15:46:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++]
---
복습문제 9번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray1.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

전에 했던 숫자채우기 for문 응용 문제 느낌이다.

```c++
int main()
{
    int arrays[4][4];
    
    int cur = 1;
    for(int i = 0; i < 4; i++)
    {
        for(int j = 0; j < 4; j++)
        {
            arrays[j][i] = cur * 2;
            cur++;
        }
    }

    for(int i = 0; i < 4; i++)
    {
        for(int j = 0; j < 4; j++)
            std::cout << arrays[i][j] << " ";

        std::cout << std::endl;
    }

    // 결과
    // 2 10 18 26
    // 4 12 20 28
    // 6 14 22 30
    // 8 16 24 32

    return 0;
}
```
---------------------------------------

# 후기

숫자채우기는 흥미로운 문제다.

