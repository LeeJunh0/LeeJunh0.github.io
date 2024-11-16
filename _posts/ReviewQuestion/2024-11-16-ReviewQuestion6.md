---
title: 기본기 복습문제6.
date: 2024-11-16 08:27:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++, ]
---
복습문제 6번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewQuestion6.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

다차원 배열을 순회하며 input의 배수들이 몇개 있는지 카운팅하여 출력하는 문제이다.

```c++
int main()
{
    int arrays[][3] =
    {
        { 3, 5, 14 },
        { 2, 3, 9 },
        { 6, 2, 7 }
    };

    int input;
    std::cin >> input;

    int count = 0;
    for(int i = 0; i < sizeof(arrays) / sizeof(arrays[0]); i++)
    {
        for(int j = 0; j < sizeof(arrays[0]) / sizeof(int); j++)
        {
            if(arrays[i][j] % input <= 0)
                count++;
        }
    }

    std::cout << count;
    return 0;
}
```
---------------------------------------

# 후기

으윽.. sizeof로 길이구하는거 점점 벅차다.. 자주쓰는데 코드가 너무 길다..
C#의 Length가 그립다.. 그냥 vector로 만들어버릴까보다...ㅠ

