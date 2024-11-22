---
title: 기본기 복습문제16.
date: 2024-11-21 11:35:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 16번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray8.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

해당 줄을 검사하는 문제로 전역배열을 검사하는데 함수의 리턴값으로만
해결하는것이 핵심인 문제2.

```c++

char arrays[3][5] =
{
    { 'D', 'A', 'C', 'C', 'D' },
    { 'S', 'D', 'F', 'A', 'E' },
    { 'E', 'E', 'T', 'J', 'H' }   
};

void InputMethod();
int Check(char input);

int main()
{
    InputMethod();
    return 0;
}

void InputMethod() 
{
    int input;
    std::cin >> input;

    int result = Check(input);
    if(result == 1)
        std::cout << "있음";
    else
        std::cout << "없음";
}

int Check(char input)
{
    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 5; j++)
        {
            if(input == arrays[i][j])
                return 1;
        }
    }

    return 0;
}
```
---------------------------------------

# 후기

리턴을 중간에 쓸수있다는것을 아는것이 중점? 인 문제인듯하다.

