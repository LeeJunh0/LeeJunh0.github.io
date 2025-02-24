---
title: Binary Search 연습문제 2
date: 2025-02-24 18:28:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, tree ]
---

이진탐색 에 익숙해지기 위한 연습문제 2 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/binarysearch2.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

void BinarySearch(string target, int start, int end, int curTime, int maxTime);

vector<string> vec;

int main()
{
    int n, m;
    cin >> n;
    for (int i = 0; i < n; i++)
    {
        string str;
        cin >> str;
        vec.emplace_back(str);
    }
    
    sort(vec.begin(), vec.end(), [](const string& a, const string& b) { return a < b;});
    
    cin >> m;
    for (int i = 0; i < m; i++)
    {
        string str;
        int time;
        cin >> str >> time;
        BinarySearch(str, 0, vec.size(), 1, time);
    }
    
    return 0;
}

void BinarySearch(string target,int start, int end, int curTime, int maxTime)
{
    int mid = (start + end) / 2;
    
    if (maxTime < curTime)
    {
        cout << "fail" << endl;
        return;
    }
    
    if (target == vec[mid])
    {
        cout << "pass" << endl;
        return;
    }
    
    if (target < vec[mid])
        BinarySearch(target, start, mid - 1, curTime + 1, maxTime);	
    else
        BinarySearch(target, mid + 1, end, curTime + 1, maxTime);
}
```
---------------------------------------

# 후기

이진탐색을 위해 사전순 오름차순 정렬을 해주고 이진탐색의 리미트를 걸어

리미트까지 답을 찾을수있는지 아닌지 출력하는 문제이다.
