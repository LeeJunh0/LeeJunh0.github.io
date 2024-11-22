---
title: 기본기 복습문제22.
date: 2024-11-21 13:35:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 22번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray14.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int main()
{
    int arrays[2][3];

    for(int i = 0; i < 2; i++)
    {
        for(int j = 0; j < 3; j++)
            std::cin >> arrays[i][j];
    }

    for(int i = 0; i < 2; i++)
    {
        for(int j = 0; j < 3; j++)
        {
            if(arrays[i][j] == 0)
                std::cout << "#";
            else
                std::cout << arrays[i][j];
        }
    }

    return 0;
}
```
---------------------------------------

# 후기

블로그에 이렇게 남기는 일도 이젠 슬슬 익숙해지는거 같다...

