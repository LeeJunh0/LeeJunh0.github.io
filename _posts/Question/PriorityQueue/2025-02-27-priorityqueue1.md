---
title: Priority_Queue 연습문제 1
date: 2025-02-27 08:30:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, Heap ]
---

우선순위 큐 에 익숙해지기 위한 연습문제 1 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/heap1.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <queue>

using namespace std;

int main()
{
    // priority_queue<char, vector<char>, less<char>>와 같음_
    priority_queue<char> pque;
    string str;
    cin >> str;
    
    for (int i = 0; i < str.length(); i++)	
        pque.push(str[i]);
    
    while (pque.empty() == false)
    {
        char ch = pque.top();
        pque.pop();
        cout << ch;
    }
    
    return 0;
}
```
---------------------------------------

# 후기

우선순위 큐에 문자열을 담고 내림차순으로 출력하는 문제로

우선순위 큐는 만들때 보면 알지만 힙이기 때문에 내부 자체에서는

완벽한 정렬모양이 나오지않는다. 그래서 디버깅때도 정렬이 안된거 처럼

보이겠지만, pop할때 최대값 혹은 최소값이 나오게 구현되어 있기때문에

출력값은 문제없게 나온다.
