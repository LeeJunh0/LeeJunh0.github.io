---
title: 기본기 복습문제18.
date: 2024-11-21 12:51:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 18번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray10.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

오랜만에 보는 플래그 코딩이다.

```c++
int main()
{
    char arr[] = { 'D', 'F', 'G', 'D', 'A', 'Q' };
    char a, b;
    std::cin >> a >> b;

    bool flag = true;
    for(int i = 0; i < sizeof(arr) / sizeof(char); i++)
    {
        if(a <= arr[i] && arr[i] <= b)
        {
            flag = true;
            break;
        }
    }

    if(flag == true)
        std::cout << "발견 !!!";
    else
        std::cout << "미발견 !!!;

    return 0;
}
```
---------------------------------------

# 후기

문제 밑에 습관에 관하여 말씀하신게 있었는데 전 잘 지키고있습니다!!

