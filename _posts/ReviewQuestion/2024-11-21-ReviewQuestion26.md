---
title: 기본기 복습문제26.
date: 2024-11-21 14:43:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 26번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray18.png){:w = "700" h = "400"}

---------------------------------------

# 풀이
최댓값 과 최솟값을 찾는 문제를 조금더 심화한 문제..? 같다.

```c++
int main()
{
    int arr[] =
    {
        { 3, 1, 6 },
        { 7, 8, 4 },
        { 9, 2, 3 }
    };

    int a, b, c;

    std::cin >> a >> b >> c;
    arrays[a][b] = c;

    int curMax = -9999;
    int curMin = 9999;
    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 3; j++)
        {
            if(curMax > arrays[i][j])
                curMax = arrays[i][j];
            
            if(curMin < arrays[i][j])
                curMin = arrays[i][j];
        }
    }

    std::cout << curMax + curMin;
    return 0;
}
```
---------------------------------------

# 후기

슬슬 어려운 문제가 나올려한다!

