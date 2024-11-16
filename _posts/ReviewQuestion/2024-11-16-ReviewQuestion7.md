---
title: 기본기 복습문제7.
date: 2024-11-16 08:42:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++, ]
---
복습문제 7번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewQuestion7.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

어우 지문이 상당히 긴데.. 요약하자면 구조체를 만들어
조건에 맞게 값을 할당하고 해당 구조체의 값들을 출력하는 문제이다.

```c++
struct PROJECT
{
    int num;
    char id;
    int vect[4];
};

int main()
{
    PROJECT z;
    
    int input;
    std::cin >> input;
    
    if (input / 100 >= 1)
    {
        z.num = 10;
        z.id = 'Q';
        z.vect[0] = 9;
        z.vect[1] = 1;
        z.vect[2] = 6;
        z.vect[3] = 2;
    }
    else if (input / 10 >= 1)
    {
        z.num = 8;
        z.id = 'T';
        z.vect[0] = 5;
        z.vect[1] = 1;
        z.vect[2] = 2;
        z.vect[3] = 3;
    }
    else
    {
        z.num = 5;
        z.id = 'G';
        z.vect[0] = 1;
        z.vect[1] = 2;
        z.vect[2] = 3;
        z.vect[3] = 4;
    }
    
    std::cout << z.id << std::endl;
    std::cout << z.num << std::endl;
    for (int i = 0; i < sizeof(z.vect) / sizeof(int); i++)
        std::cout << z.vect[i] << " ";
    
    return 0;
}
```
---------------------------------------

# 후기

하드코딩때문에 코드가 많아 보이지만 최선이지 않을까 싶다..!

