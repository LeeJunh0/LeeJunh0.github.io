---
title: BruteForce 연습문제 1
date: 2025-03-01 18:50:00 +0900
categories: [Question]  
tags:  [ C, C++, BFS]
---

완전탐색에 익숙해지기 위한 연습문제 1 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/bruteforce1.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>

using namespace std;

void Recursion(int cur, int num);

int n;
int cnt = 0;

int main()
{
    cin >> n;
    Recursion(0, 0);
    cout << cnt;
    return 0;
}

void Recursion(int cur, int num)
{
    if (cur == n)
    {
        if(num == 7)
            cnt++;
        
        return;
    }
    
    for (int i = 0; i < 9; i++)
        Recursion(cur + 1, num + i);
}
```
---------------------------------------

# 후기

BruteForce 완전탐색은 알고리즘이나 방법들과 다르게 개념영역에 속한다.

보통 많은 양의 계산을 하기 때문에 주로 DFS나 BFS를 써서 많이 구현한다.

이번 문제는 그런 완전탐색을 알기 위한 문제였다.
