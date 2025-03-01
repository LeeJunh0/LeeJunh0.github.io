---
title: BruteForce 연습문제 2
date: 2025-03-01 18:59:00 +0900
categories: [Question]  
tags:  [ C, C++, BFS]
---

완전탐색에 익숙해지기 위한 연습문제 2 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/bruteforce2.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>

using namespace std;

void Recursion(int cur, string path);

string str = "";

int main()
{
    cin >> str;
    Recursion(0, "");
    return 0;
}

void Recursion(int cur, string path)
{
    if (cur == 3)
    {
        cout << path << endl;
        return;
    }
    
    for (int i = 0; i < str.length(); i++)
    {
        path.push_back(str[i]);
        Recursion(cur + 1, path);
        path.pop_back();
    }
}
```
---------------------------------------

# 후기

재료들이 중복으로 들어가도 되는 김밥을 만들수 있는 모~든 경우의수를

출력하는 문제다. 문제는 브루트포스지만 코드는 백트래킹이다..
