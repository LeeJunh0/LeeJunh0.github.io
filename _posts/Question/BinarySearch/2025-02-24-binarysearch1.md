---
title: Binary Search 연습문제 1
date: 2025-02-24 00:13:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, tree ]
---

이진탐색 에 익숙해지기 위한 연습문제 1 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/binarysearch1.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <vector>

using namespace std;

void BinarySearch(int start, int end);

int arr[11] = { 4,4,5,7,8,10,20,22,23,24 };
int target;

int main()
{
    cin >> target;
    BinarySearch(0, 10);
    return 0;
}

void BinarySearch(int start, int end)
{
    int mid = (start + end) / 2;
    
    if (arr[mid] == target)
    {
        cout << "O" << endl;
        return;
    }
    
    if (mid == start)
    {
        cout << "X" << endl;
        return;
    }
    
    if (target > arr[mid])
        BinarySearch(mid + 1, end);
    else
        BinarySearch(start, mid - 1);
}
```
---------------------------------------

# 후기

이진탐색을 만들어 입력값의 존재 여부를 출력하는 문제다.

이제 잘 할수있게된 재귀로 쉽게 풀었다.
