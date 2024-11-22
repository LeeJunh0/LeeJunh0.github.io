---
title: 기본기 복습문제20.
date: 2024-11-21 13:13:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 20번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray12.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int main()
{
    char arr[] = { 'A', '1', '1', '1', '5', 'A', 'w', 'z' };
    char input;
    std::cin >> input;

    int count = 0;
    for(int i = 0; i < sizeof(arr) / sizeof(char); i++)
    {
        if(arr[i] == input)
            count++;
    }

    if(count >= 3)
        std::cout << "THREE";
    else if(count >= 2)
        std::cout << "TWO";
    else if(count >= 1)
        std::cout << "ONE";
    else
        std::cout << "NOTHING";

    return 0;
}
```
---------------------------------------

# 후기

블로그에 이렇게 남기는 일도 이젠 슬슬 익숙해지는거 같다.

