---
title: 기본기 복습문제4.
date: 2024-11-16 07:59:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++, ]
---
복습문제 4번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewQuestion4.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

다차원 배열을 순회하면서 두 조건에 모두 맞으면 카운팅하고
순회가 끝나면 카운트를 출력하면 되는 문제같다.

```c++
int main()
{
    int arrays[3][3] = 
    {
        { 10, 3, 20 },
        { 60, 30, 40 },
        { 20, 30, 40 }
    };

    int a, b;
    scanf("%d %d", &a, &b);

    for(int i = 0 ; i < sizeof(arrays) / sizeof(arrays[0]); i++)
    {
        for(int j = 0; j < sizeof(arrays[0]) / sizeof(int); j++)
        {
            if(a <= arrays[i][j] && arrays[i][j] <= b)
                count++;
        }
    }

    std::cout << count;
    return 0;
}
```
---------------------------------------

# 후기

슬슬 논리연산자도 같이 쓰는 문제가 나온다!

