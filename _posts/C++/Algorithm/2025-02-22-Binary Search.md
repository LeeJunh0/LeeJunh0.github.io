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

-------------------------------
![DeskTop View](/assets/img/binarysearch.png){: w= "500" h= "350"}

-------------------------------

1. 정렬된 배열의 전체길이의 중간 index를 찾는다.

2. 중간 index 값과 목표 값을 비교한다.

3. 중간 index 값보다 목표 값이 작으면 왼쪽, 아니면 오른쪽으로 탐색한다.

4. 더 이상 탐색범위가 없을때까지 이걸 반복한다.

-------------------------------

```c++
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

## 이진탐색의 Lower, Upper bound 개념과 구현
--------------------------------------

탐색할 컨테이너에 원하는 값이 딱 1개만 있을때는 이 개념은 필요 하지않다.

이 개념이 필요할 때는 중복된 값이 있고 그 값의 범위를 찾아야 할때다.

-------------------------------
![DeskTop View](/assets/img/lower_upper.png){: w= "700" h= "350"}

--------------------------------

이런 모양으로 Lower일땐 범위의 시작인덱스, Upper일땐 범위를 벗어난 시작인덱스를 찾는다.

Lower와 Upper는 거의 흡사하지만 쪼금 다르니 잘 봐야한다. 만들어 보는걸 추천한다.


```c++
// Lower 범위의 시작을 찾는다.
void Lower(int start, int end, int n)
{
    int left = start;
    int right = end;

    while (left < right)
    {
        int mid = (left + right) / 2;

        if (arr[mid] < n)
            left = mid + 1;
        else
            right = mid;
    }
}

// Upper 범위를 벗어난 시작을 찾는다.
void Upper(int start, int end, int n)
{
    int left = start;
    int right = end;

    while (left < right)
    {
        int mid = (left + right) / 2;

        // 범위밖 까지 가야 하기 때문에 <=
        if (arr[mid] <= n)
            left = mid + 1;
        else
            right = mid;
    }
}
```
