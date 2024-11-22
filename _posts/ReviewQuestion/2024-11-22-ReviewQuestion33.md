---
title: 기본기 복습문제33.
date: 2024-11-22 22:54:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 33번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/Reviewstring6.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int main()
{
    char vect[100];
    std::cin >> vect;

    int length = 0;
    int count = 0;
    for(int i = 0; vect[i] != '\0'; i++)
        length++;


    char last = vect[length - 1];
    for(int i = 0; i < length; i++)
    {
        if(last == vect[i])
            count++;
    }

    std::cout << length << std::endl;
    std::cout << count << std::endl;

    // 입력 : HappyCap
    // 결과
    // 8
    // 3

    return 0;
}
```
---------------------------------------

# 후기

길이를 구하고 마지막 문자 몇개있는지 체크하는데 이렇게 귀찮을줄이야..

