---
title: Binary Search(이진탐색) 란?
date: 2025-02-23 20:52:00 +0900
categories: [C++]  
tags:  [ Algorithm ]
---

## 이진탐색은 무엇일까?
-------------------------------

이진탐색은 정렬돼 있는 데이터에서 값을 찾는 알고리즘이다.

이진탐색은 이분탐색이라고도 불리는데, 탐색범위를 반으로 나누어 값을

좁혀가는 방식으로 동작하기 때문이다. 주로 배열의 인덱스를 기준으로

배열 내의 값을 탐색하는데 사용되지만 리스트, 트리 등에서도 사용할 수 있다.


## 이진탐색의 동작방식을 보자
-------------------------------

![DeskTop View](/assets/img/binarysearch.png){: w= "500" h= "350"}

-------------------------------

1. 정렬된 배열의 전체길이의 중간 index를 찾는다.

2. 중간 index 값과 목표 값을 비교한다.

3. 중간 index 값보다 목표 값이 작으면 왼쪽, 아니면 오른쪽으로 탐색한다.

4. 더 이상 탐색범위가 없을때까지 이걸 반복한다.

-------------------------------

```c++
#include <iostream>
#include <vector>

using namespace std;

void Recursion(int start, int end);

int vec[9] = { 1, 2, 3, 4, 5, 6, 7, 8 };
int target = 2;

int main()
{
    Recursion(0, 9);
    return 0;
}

void Recursion(int start, int end)
{
    int mid = (start + end) / 2;
    
    if(vec[mid] == target)
    {
        cout << "타겟 찾음" << endl;
        return;
    }

    if(target > vec[mid])
        Recursion(mid + 1, end);
    else
        Recursion(start, mid - 1);
}
```


