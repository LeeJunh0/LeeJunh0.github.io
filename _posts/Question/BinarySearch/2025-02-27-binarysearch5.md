---
title: Binary Search 연습문제 5
date: 2025-02-27 07:43:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, tree ]
---

이진탐색 에 익숙해지기 위한 연습문제 5 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/binarysearch5.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <vector>

using namespace std;

void BinarySearch(int start, int end);
int n;

int main()
{
    cin >> n;
    BinarySearch(1, n);
    
    return 0;
}

void BinarySearch(int start, int end)
{
    int mid = (start + end) / 2;
    
    if (start > end)
    {
        cout << end << endl;
        return;
    }
    
    if (mid * mid == n)
    {
        cout << mid << endl;
        return;
    }
    
    if (mid * mid < n)
        BinarySearch(mid + 1, end);
    else
        BinarySearch(start, mid - 1);
}
```
---------------------------------------

# 후기

입력값 N의 루트 값을 Binary Search로 구해야 하는 문제입니다.

mid제곱이 n가 같다면 mid가 제곱근에 해당하지만 딱 떨어지지 않는

경우에는 모든 탐색을 완료했을때 end가 가장 근사값이 되어 end를

출력하면 되는 문제입니다.
