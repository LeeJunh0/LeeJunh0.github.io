---
title: 기본기 복습문제34.
date: 2024-11-22 23:14:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 34번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/Reviewstring7.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int main()
{
    char arr1[50];
    char arr2[50];
    char arr3[50];
    
    std::cin >> arr1 >> arr2 >> arr3;
    
    int length1 = 0;
    int length2 = 0;
    int length3 = 0;
    
    for (int i = 0; arr1[i] != '\0'; i++)
        length1++;
    for (int i = 0; arr2[i] != '\0'; i++)
        length2++;
    for (int i = 0; arr3[i] != '\0'; i++)
        length3++;
    
    int big = length1 > length2 ? length1 : length2;
    big = big > length3 ? big : length3;
    
    if (length1 == big)	
        std::cout << arr1;
    else if (length2 == big)	
        std::cout << arr2;
    else
        std::cout << arr3;
    
    // 입력
    // BBQ
    // CODING
    // HAPPYCAT

    // 결과
    // HAPPYCAT

    return 0;
}
```
---------------------------------------

# 후기

와... 정말 역대급 노가다 문제였다.

