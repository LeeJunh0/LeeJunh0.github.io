---
title: Priority_Queue 연습문제 3
date: 2025-02-27 15:57:00 +0900
categories: [Question]  
tags:  [ C, C++, Algorithm, Heap ]
---

우선순위 큐 에 익숙해지기 위한 연습문제 3 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/heap3.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------

```c++
#include <iostream>
#include <queue>

using namespace std;

struct Item
{
    string type;
    int weight;
    
    Item(string t, int w) : type(t), weight(w) {}
    
    bool operator>(const Item& ref) const
    {
        return weight > ref.weight;
    }
    
    bool operator<(const Item& ref) const
    {
        return weight < ref.weight;
    }
};

int main()
{
    priority_queue<Item, vector<Item>,greater<Item>> pq;
    
    int n;
    cin >> n;
    for (int i = 0; i < n; i++)
    {
        int value;
        cin >> value;
        pq.push(Item("gold", value));
    }
    
    int count = 0;
    while (pq.empty() == false)
    {
        Item first = pq.top();
        if (first.type == "stone")
            break;
        else
        {
            pq.pop();
            count++;
        }
        
        Item second = pq.top();
        if (second.type == "stone")
            break;
        else
        {
            pq.pop();
            count++;
            pq.push(Item("stone", second.weight * 2));
        }
    }
    
    cout << count;
    return 0;
}
```
---------------------------------------

# 후기

주머니 속 물품의 타입과 무게를 담는 구조체를 만들어 우선순위 큐에 

오름차순에 쓸 연산자를 무게를 기준으로 할수있게 오버로드 해주고

황금인지 돌인지 조건을 걸어 구현했다.
