---
title: 기본기 복습문제30.
date: 2024-11-22 22:29:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 30번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/Reviewstring3.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
char arrays[4][3] =
{
    { 'D', 'A', 'D' },
    { 'Q', 'W', 'Q' },
    { 'A', 'S', 'D' },
    { 'A', 'S', 'D' }
};

void Find(char input);

int main()
{
    char input;
    std::cin >> input;
    Find(input);
    
    // 입력 : T
    
    // 결과
    // 없음

    return 0;
}

void Find(char input)
{
    for (int i = 0; i < sizeof(arrays) / sizeof(arrays[0]); i++)
    {
        for (int j = 0; j < sizeof(arrays[0]) / sizeof(char); j++)
        {
            if (input == arrays[i][j])
            {
                std::cout << "존재";
                return;
            }
        }
     }

    std::cout << "없음";
}
```
---------------------------------------

# 후기

다시 돌아온 찾기 문제

