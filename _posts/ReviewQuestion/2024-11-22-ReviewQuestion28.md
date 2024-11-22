---
title: 기본기 복습문제27.
date: 2024-11-21 15:32:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 27번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray19.png){:w = "700" h = "400"}

---------------------------------------

# 풀이
숫자 채우기, 배열복사, swap, 까지 활용하는 응용문제다.

```c++
int main()
{
    int arrays[2][3];

    int y = sizeof(arrays) / sizeof(arrays[0]);
    int x = sizeof(arrays[0]) / sizeof(int);
    for(int i = y - 1; i >= 0; i--)
    {
        for(int j = x - 1; j >= 0; j--)
            std::cin >> arrays[i][j];
    }

    int tempArr[6];
    int idx = 0;
    for(int i = 0; i < y; i++)
    {
        for(int j = 0; j < x; j++)
        {
            tempArr[idx] = arrays[i][j];
            idx++;
        }
    }

    int temp = tempArr[0];
    tempArr[0] = tempArr[5];
    tempArr[5] = temp;

    for(int i = 0; i < sizeof(tempArr) / sizeof(int); i++)
        std::cout << tempArr[i] << " ";

    return 0;
}
```
---------------------------------------

# 후기

생각을 찌금은 해야하는 문제였다.

