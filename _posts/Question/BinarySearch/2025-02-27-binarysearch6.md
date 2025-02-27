---
title: Binary Search 연습문제 6
date: 2025-02-27 07:55:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, tree ]
---

이진탐색 에 익숙해지기 위한 연습문제 6 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/binarysearch6.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <vector>

using namespace std;

void BinarySearch(int start, int end);

string fual;

int main()
{	
    cin >> fual;
    BinarySearch(0, fual.length());
    return 0;
}

void BinarySearch(int start, int end)
{
    int mid = (start + end) / 2;
    
    if (start > end)
    {
        cout << start * 10 << "%";
        return;
    }
    
    if (fual[mid] == '#')
        BinarySearch(mid + 1, end);
    else
        BinarySearch(start, mid - 1);
}
```
---------------------------------------

# 후기

주유량을 입력값으로 받고 현재 주유량이 몇 %인지 출력하는 문제로

탐색할 범위가 없을때 까지 탐색한 후의 기름이 차있는 량을 알려주는 start에 

10을 곱하면 답이 나오게 되어있다.
