---
title: Binary Search 연습문제 4
date: 2025-02-24 19:46:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, tree ]
---

이진탐색 에 익숙해지기 위한 연습문제 4 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/binarysearch4.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

void BinarySearch(int start, int end, int y);

vector<string> vecs(5);

int main()
{
    for (int i = 0; i < 5; i++)
    {
        cin >> vecs[i];
        sort(vecs[i].begin(), vecs[i].end(), [](const char& a, const char& b) { return a < b; });
    }
    
    for (int i = 0; i < 5; i++)
        BinarySearch(0, vecs[i].size(), i);
    
    return 0;
}

void BinarySearch(int start, int end, int y)
{
    int mid = (start + end) / 2;
    
    if (mid == vecs[y].size() - 1 || start == mid && vecs[y][mid] == '*')
    {
        cout << 1 + mid << endl;
        return;
    }
    else if (vecs[y][mid] == '*')
        BinarySearch(mid + 1, end, y);
    else
        BinarySearch(start, mid - 1, y);
}

```
---------------------------------------

# 후기

상처 길이를 구해야 하는 문제로 각 행을 정렬한 다음 이진탐색으로 길이를 구해준다.

1. mid Index가 현재 행의 끝까지 갔거나, start와 같은지 확인

2. 이후 mid Index가 상처인지 확인

이 조건이 부합하면 거기가 마지막 상처다.

이후 출력은 1 + mid Index를 하면 그게 길이다.
