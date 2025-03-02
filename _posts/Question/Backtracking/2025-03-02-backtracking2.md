---
title: BackTracking 연습문제 2
date: 2025-03-02 16:20:00 +0900
categories: [Question]  
tags:  [ C, C++, BackTracking ]
---

백트래킹에 익숙해지기 위한 연습문제 2 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/backtracking2.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>
#include <vector>

using namespace std;

void Recursion(int cur);

vector<int> path;
vector<int> vec(5);
vector<int> visited(5);

int maxResult = 0;
int minResult = 99;

int main()
{
    for (int i = 0; i < 5; i++)
        cin >> vec[i];
    
    Recursion(0);
    cout << maxResult << endl;
    cout << minResult << endl;
    
    return 0;
}

void Recursion(int cur)
{
    if (cur == 5)
    {
        int num = (path[0] * path[1]) - (path[2] * path[3]) + path[4];
        
        maxResult = max(num, maxResult);
        minResult = min(num, minResult);
        
        return;
    }
    
    for (int i = 0; i < 5; i++)
    {
        if (visited[i] == 1)
            continue;
        
        visited[i] = 1;
        path.emplace_back(vec[i]);
        
        Recursion(cur + 1);
        
        visited[i] = 0;
        path.pop_back();
    }
}
```
---------------------------------------

# 후기

상당히 오래걸려 풀었는데 이유가 문제의 요점을 잘못 집었다..

이 문제의 핵심은 연산자들은 전부 고정되있으며 바뀌는건 순열이다.

즉, 백트레킹으로 순열을 계속 바꿔가며 최소 최대값을 구하는것이였다.
