---
title: 기본기 복습문제2.
date: 2024-11-16 06:57:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++, ]
---
복습문제 2번이다. 상당히 해야하는게 많다.

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewQuestion2.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

배열에서 A라는 문자가 몇개 존재하는지 출력하고
그 후 A의 index도 출력해줘야 한다.

```c++
int main()
{
    char arr[5];
    int indexArr[sizeof(arr) / sizeof(char)];
    scanf("%c %c %c %c %c", &arr[0], &arr[1], &arr[2], &arr[3], %arr[4]);

    int count = 0;
    int indexCount = 0;
    for(int i = 0; i < sizeof(arr) / sizeof(char); i++)
    {
        if('A' == arr[i])
        {
            count++;
            indexArr[indexCount] = i;
            indexCount++;
        }
    }

    printf("문자A는 %d개발견", count);

    for(int i = 0; i < count; i++)
        printf("%d번",indexArr[i]);

    return 0;
}
```
---------------------------------------

# 후기

체크하기위한 변수가 많아졌고 신경쓸게 전 보다 많아졌다.

