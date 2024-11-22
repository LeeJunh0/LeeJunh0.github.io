---
title: 기본기 복습문제23.
date: 2024-11-21 13:59:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 23번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray15.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++

void CompareGo(int arr[], int temp[]);

int main()
{
    int arr[5] = { 3, 5, 1, 2, 7 };
    int temp[5];

    for(int i = 0; i < 5; i++)
        std::cin >> temp[i];
    
    CompareGo(arr, temp);
    return 0;
}

void CompareGo(int arr[], int temp[])
{
    bool flag = true;
    for(int i = 0; i < sizeof(arr) / sizeof(int); i++)
    {
        if(arr[i] != temp[i])
        {
            flag = false;
            break;
        }
    }

    if(flag == true)
        std::cout << "두배열은완전같음";
    else
        std::cout << "두배열은같지않음";
}
```
---------------------------------------

# 후기

플래그 기법을 사용하는 문제는 넘 노가다다.

