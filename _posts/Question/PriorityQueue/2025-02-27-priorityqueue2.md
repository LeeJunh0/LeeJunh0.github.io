---
title: Priority_Queue 연습문제 2
date: 2025-02-27 09:08:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, Heap ]
---

우선순위 큐 에 익숙해지기 위한 연습문제 2 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/heap2.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <vector>
#include <queue>

using namespace std;

struct heap
{
    int price;
    char ch;
    char link;
    
    heap(int value, char a, char b) : price(value), ch(a), link(b) {}
    
    bool operator<(const heap& ref) const
    {
        return price < ref.price;
    }
};

int main()
{
    int n;
    cin >> n;
    priority_queue<heap> pq;
    vector<vector<int>> graph(n, vector<int>(n));
    
    for (int i = 0; i < n; i++)
    {
        for(int j = 0; j < n; j++)
        {
            int price;
            cin >> price;
            graph[i][j] = price;
        }
    }
    
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < n; j++)
        {
            heap h(graph[i][j], i + 65, j + 65);
            pq.push(h);
        }
    }
    
    for (int i = 0; i < 3; i++)
    {
        heap h = pq.top();
        pq.pop();
        cout << h.ch << "->" << h.link << " " << h.price << endl;
    }
    
    return 0;
}
```
---------------------------------------

# 후기

구조체에 정보를 저장하고 우선순위 큐에 구조체를 넣어

가장 큰 3개만 출력하면 되는문제로 구조체에 연산자를 오버로딩해서

우선순위 큐의 내림차순 정렬을 바꿔서 풀었다.
