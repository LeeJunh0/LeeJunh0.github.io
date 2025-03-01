---
title: BackTracking 연습문제 1
date: 2025-03-01 19:30:00 +0900
categories: [Question]  
tags:  [ C, C++, BFS]
---

백트래킹에 익숙해지기 위한 연습문제 1 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/backtracking1.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>
#include <vector>

using namespace std;

void Recursion(int cur);

vector<string> vec = {"북이", "찍이", "토이", "숭이", "뽀삐", "냥이"};
vector<string> path;
vector<int> visited(6);

int a, b;
int cnt = 0;

int main()
{
    cin >> a >> b;
    Recursion(0);
    cout << cnt;
    return 0;
}

void Recursion(int cur)
{
    if (cur == 6)
    {
        cnt++;
        return;
    }
    
    for (int i = 0; i < 6; i++)
    {
        if (visited[i] == 1)
            continue;
        
        if ((cur == a - 1 || cur == b - 1) && vec[i] == "뽀삐")
            continue;
        
        path.emplace_back(vec[i]);
        visited[i] = 1;
        
        Recursion(cur + 1);
        
        path.pop_back();
        visited[i] = 0;
    }
}
```
---------------------------------------

# 후기

백트래킹은 브루트포스의 단점을 보완한 탐색기법으로

미리 답이 되지않을꺼같은 쪽은 가지않는 기법으로 불필요한

탐색을 줄이는 방법이다. 이 문제에서는 뽀삐가 1등 6등이면

미리 가지않게 처리해서 풀었다.
