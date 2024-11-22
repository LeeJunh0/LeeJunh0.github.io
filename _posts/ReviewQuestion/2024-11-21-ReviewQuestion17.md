---
title: 기본기 복습문제17.
date: 2024-11-21 11:50:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 17번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray9.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

배열을 조건에 맞는 형태로 채우는 문제이다.

```c++

void Run(int input);

int main()
{
    int input;
    std::cin >> input;
    Run(input);

    return 0;
}

void Run(int input)
{
    int arrays[3][3];

    int cur = 1;
    int length = sizeof(arrays) / sizeof(arrays[0]);
    if(input < 10)
    {
        for(int i = 0; i < length; i++)
        {
            for(int j = 0; j < length; j++)
            {
                arrays[i][j] = cur;
                cur++;
            }
        }
    }
    else
    {
        for(int i = 0; i < length; i++)
        {
            for(int j = length - 1; j >= 0; j--)
            {
                arrays[i][j] = cur;
                cur++;
            }
        }
    }

    for(int i = 0; i < length; i++)
    {
        for(int j = 0; j < length; j++)
            std::cout << arrays[i][j];
        
        std::cout << std::endl;
    }
}
```
---------------------------------------

# 후기

숫자채우기의 심화버전인듯 하다.

