---
title: 기본기 복습문제3.
date: 2024-11-16 07:24:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++, ]
---
복습문제 3번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewQuestion3.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

이번엔 좌표를 출력하는 문제로 i, j를 출력하는거같다.

```c++
int main()
{
    char arrays[][3] =
    {
        { 'D', 'A', 'A' },
        { 'B', 'C', 'D' },
        { 'E', 'F', 'A' },
        { 'A', 'A', 'D' },
        { 'F', 'G', 'E' }
    };

    char input;
    std::cin >> input;

    for(int i = 0; i < sizeof(arrays) / sizeof(char); i++)
    {
        for(int j = 0; j < sizeof(arrays[0]) / sizeof(char); j++)
        {
            if(input == arrays[i][j])
                printf("(%d,%d)\n", i, j);
        }
    }

	  return 0;
}
```
---------------------------------------

# 후기

확실히 난이도가 전보단 올랐다.

