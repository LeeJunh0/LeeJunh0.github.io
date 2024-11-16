---
title: 기본기 복습문제5.
date: 2024-11-16 08:12:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++, ]
---
복습문제 5번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewQuestion5.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

전역으로 선언된 다차원배열을 함수들 안에서 순회하며 조건에 맞게 
카운팅하고 카운트를 출력하는 문제같다.


```c++
void FindUpper();
void FindLower();

char arrays[2][3];

int main()
{
    for(int i = 0 ; i < sizeof(arrays) / sizeof(arrays[0]); i++)
    {
        for(int j = 0; j < sizeof(arrays[0]) / sizeof(char); j++)
            std::cin >> arrays[i][j];
    }

    FindUpper();
    FindLower();
    return 0;
}

void FindUpper()
{
    int count = 0;
    for(int i = 0 ; i < sizeof(arrays) / sizeof(arrays[0]); i++)
    {
        for(int j = 0; j < sizeof(arrays[0]) / sizeof(char); j++)
        {
            if(97 > arrays[i][j])
                count++;
        }
    }

    printf("대문자는%d개\n", count);
}

void FindLower()
{
    int count = 0;
    for(int i = 0 ; i < sizeof(arrays) / sizeof(arrays[0]); i++)
    {
        for(int j = 0; j < sizeof(arrays[0]) / sizeof(char); j++)
        {
            if(97 <= arrays[i][j])
                count++;
        }
    }

    printf("소문자는%d개\n", count);
}
```
---------------------------------------

# 후기

으으 중복코드가 너무많다... 재사용성이 구리다..

