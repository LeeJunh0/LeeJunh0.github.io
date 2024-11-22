---
title: 기본기 복습문제21.
date: 2024-11-21 13:21:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 21번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray13.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int main()
{
    char arrays[3][5] = 
    {
        { 'a', 'b', 'a', 'c', 'z' },
        { 'c', 't', 'a', 'c', 'd' },
        { 'c', 'c', 'c', 'c', 'a' }
    }

    char input;
    std::cin >> input;

    int count = 0;
    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 5; j++)
        {
            if(arrays[i][j] == input)
                count++;
        }
    }

    if(count >= 7)
        std::cout << "세상에";
    else if(count >= 5)
        std::cout << "와우";
    else if(count >= 3)
        std::cout << "이야";
    else
        std::cout << "이런";

    return 0;
}
```
---------------------------------------

# 후기

블로그에 이렇게 남기는 일도 이젠 슬슬 익숙해지는거 같다..

