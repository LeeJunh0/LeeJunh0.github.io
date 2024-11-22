---
title: 기본기 복습문제25.
date: 2024-11-21 14:20:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 25번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray17.png){:w = "700" h = "400"}

---------------------------------------

# 풀이
플래그 코딩이지만 캐스팅을 섞은 문제다!

```c++

char arrays[3][3] = 
{
    { 'a', 'b', 'd' },
    { 'e', 'w', 'z' },
    { 'q', 'v', 'a' }
};

void InputMethod();
void ProcessMethod(char input);

int main()
{
    InputMethod();
    return 0;
}

void InputMethod()
{
    char input;
    std::cin >> input;
    ProcessMethod(input);
}

void ProcessMethod(char input)
{
    char changeChar = (char)(input + 32);

    bool flag = false;

    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 3; j++)
        {
            if(arrays[i][j] == chargeChar)
            {
                flag = true;
                break;
            }
        }
    }

    if(flag == true)
        std::cout << "존재";
    else
        std::cout << "없음";
}
```
---------------------------------------

# 후기

슬슬 어려운 문제가 나올려한다!

