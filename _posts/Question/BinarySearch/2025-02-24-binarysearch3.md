---
title: Binary Search 연습문제 3
date: 2025-02-24 19:05:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, tree ]
---

이진탐색 에 익숙해지기 위한 연습문제 3 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/binarysearch3.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <vector>

using namespace std;

void BinarySearch(int y, int start, int end);

vector<vector<char>> vecs;

int main()
{
    int n;
    cin >> n;

    for (int i = 0; i < n; i++)
    {
        vecs.emplace_back(vector<char>());
        for (int j = 0; j < n; j++)
        {
            char ch;
            cin >> ch;
            vecs[i].emplace_back(ch);
        }
    }
    
    BinarySearch(0, 0, vecs.size());
    return 0;
}

void BinarySearch(int y, int start, int end)
{
    int mid = (start + end) / 2;
    
    if (mid + 1 < vecs.size() && vecs[y][mid] == '#' && vecs[y][mid + 1] == '0')
    {
        cout << y << " " << mid;
        return;
    }
    else if (mid >= vecs.size() - 1 && '#' == vecs[y][mid])
        BinarySearch(y + 1, 0, vecs.size());
    else if ('#' == vecs[y][mid])
        BinarySearch(y, mid + 1, end);
    else
        BinarySearch(y, start, mid - 1);
}
```
---------------------------------------

# 후기

데이터의 마지막이 어디인지를 확인하는 문제로 이진탐색을 사용하여 각 행의 마지막 데이터가

어디있는지 찾아야한다. 마지막 데이터의 위치추적 조건은

1. mid + 1이 '0'이여야한다.

2. mid는 '#'이여야한다.

3. 1번과 2번을 조건에 맞으면서 mid가 start와 같으면 안된다. (같으면 mid + 1에서 터진다.)

위 조건들을 전부 부합하면 마지막 데이터의 위치가 된다.
