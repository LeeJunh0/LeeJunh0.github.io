---
title: 기본기 복습문제8.
date: 2024-11-16 08:59:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++, ]
---
복습문제 8번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewQuestion8.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

홀수와 짝수를 구별해서 함수를 실행시키는 문제이다.

```c++
void BBQ(int input);
void KFC(char input);

int main()
{
    int input;
    std::cin >> input;
    
    if (input % 2 == 1)
    {
        int plusInput;
        std::cin >> plusInput;
        BBQ(plusInput);
    }
    else
    {
        char plusInput;
        std::cin >> plusInput;
        KFC(plusInput);
    }

    return 0;
}

void BBQ(int input)
{
    for (int i = 1; i <= input; i++)
        std::cout << i;
}

void KFC(char input)
{
    for (int i = 0; i < 7; i++)
        std::cout << input;
}
```
---------------------------------------

# 후기

흠 중복코드가 너무너무많다 ..

