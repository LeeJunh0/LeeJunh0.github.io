---
title: 기본기 복습문제1.
date: 2024-11-16 06:35:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++, ]
---
복습문제 1번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewQuestion1.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

배열 2개를 탐색해서 input을 전부 카운팅 하는 문제다.

```c++
int main()
{
    int arr1[] = { 2, 1, 2, 4, 5 };
    int arr2[][3] =
    {
        { 2, 5, 3 },
        { 4, 5, 7 },
        { 8, 7, 2 }
    };

    int input;
    std::cin >> input;

    int count = 0;
    for(int i = 0; i < sizeof(arr1) / sizeof(int); i++)
    {
        if(input == arr1[i])
            count++;
    }

    for(int i = 0; i < sizeof(arr2) / sizeof(arr2[0]); i++)
    {
        for(int j = 0; j < sizeof(arr2[0]) / sizeof(int); j++)
        {
            if(input == arr2[i][j])
                count++;
        }
    }

    std::cout << count;
    return 0;
}
```
---------------------------------------

# 후기

확실히 난이도가 전보단 올랐다.

