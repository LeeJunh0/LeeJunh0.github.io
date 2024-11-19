---
title: 기본기 복습문제15.
date: 2024-11-19 17:10:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 15번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray7.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

해당 줄을 검사하는 문제로 전역배열을 검사하는데 함수의 리턴값으로만
해결하는것이 핵심인 문제.

```c++

int arrays[7][5] =
{
    { 1, 0, 0, 0, 0 },
    { 1, 0, 1, 0, 0 },
    { 1, 1, 0, 1, 0 },
    { 1, 0, 1, 0, 0 },
    { 0, 1, 0, 0, 1 },
    { 0, 0, 0, 1, 0 },
    { 1, 1, 0, 0, 0 }
};

int InputMethod();
int ProcessMethod(int line);
void OutputMethod(int count);

int main()
{
    OutputMethod(ProcessMethod(InputMethod()));
    return 0;
}

int InputMethod() 
{
    int input;
    std::cin >> input;
    return input;
}

int ProcessMethod(int line) 
{
    int count = 0;
    for (int i = 0; i < 7; i++)
    {
        if (arrays[i][line] == 1)
            count++;
    }

    return count;
}

void OutputMethod(int count) 
{
    std::cout << count;
}
```
---------------------------------------

# 후기

아주 재밌는 코드가 됐다 ㅎㅎ

