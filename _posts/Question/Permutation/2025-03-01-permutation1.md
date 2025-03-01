---
title: 순열 연습문제 1
date: 2025-03-01 14:51:00 +0900
categories: [Question]  
tags:  [ C, C++, Permutation ]
---

순열 연습문제 1 !

# 문제   
---------------------------------------

![Desktop View](/assets/img/permutation1.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>
#include <vector>

using namespace std;

void Recursion(int cur);

string str = "";
string cards = "";
vector<int> visited;

int main()
{
    for (int i = 0; i < 3; i++)
    {
        char ch;
        cin >> ch;
        str += ch;
        visited.emplace_back(0);
    }
    
    Recursion(0);
    return 0;
}

void Recursion(int cur)
{
    if (cur == 3)
    {
        cout << cards << endl;
        return;
    }
    
    for (int i = 0; i < 3; i++)
    {
        if (visited[i] == 1)
            continue;
        
        visited[i] = 1;
        cards.push_back(str[i]);
        
        Recursion(cur + 1);
        
        visited[i] = 0;
        cards.pop_back();
    }
}
```
---------------------------------------

# 후기

입력받은 3장의 카드의 순열을 출력하는 문제로 

전에는 개념을 모르고 만든 코드들이였지만 재귀에

백트레킹을 적용한 코드였다! 진행할수 없을때가 되면

전 단계로 돌아가 다른 경로를 탐색하는 개념이 백트레킹이다.




