---
title: 기본기 복습문제19.
date: 2024-11-21 13:05:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 19번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray11.png){:w = "700" h = "400"}

---------------------------------------

# 풀이

```c++
int arrays[3][3] = 
{
    { 1, 1, 1 },
    { 1, 2, 1 },
    { 3, 6, 3 }
};

int Count(int input);

int main()
{
    int input;
    std::cin >> input;
    std::cout << Count(input);

    return 0;
}

int Count(int input)
{
    int count = 0;
    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 3; j++)
        {
            if(arays[i][j] == input)
                count++;
        }
    }

    return count;
}
```
---------------------------------------

# 후기

숙제는 문제를 풀면서 1번, 디버깅하면서 1번, 블로그에 작성할때 1번 해서 총 3번을 풀면서 진행하고있습니다.

