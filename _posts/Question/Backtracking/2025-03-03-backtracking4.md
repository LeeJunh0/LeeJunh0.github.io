---
title: BackTracking 연습문제 4
date: 2025-03-03 16:03:00 +0900
categories: [Question]  
tags:  [ C, C++, BackTracking ]
---

백트래킹에 익숙해지기 위한 연습문제 4 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/backtracking4.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>
#include <vector>

using namespace std;

void Recursion(int cur, int num);

vector<string> op = { "!!","#","$","&","^" };
vector<int> visited(5);
int arr[3];
int cnt = 0;

int main()
{
    for (int i = 0; i < 3; i++)
        cin >> arr[i];
    
    Recursion(1, arr[0]);
    cout << cnt;
    return 0;
}

void Recursion(int cur, int num)
{
    if (cur == 3)
    {
        if (num > 20)
            cnt++;
        
        return;
    }
    
    for (int i = 0; i < op.size(); i++)
    {
        int opNum = num;
        if (op[i] == "!!")
            opNum += arr[cur] + arr[cur];
        else if (op[i] == "#")
            opNum -= arr[cur] + arr[cur];
        else if (op[i] == "$")
            opNum += 10;
        else if (op[i] == "&")
            opNum += (arr[cur] * arr[cur]);
        else
            return;
        
        Recursion(cur + 1, opNum);
    }
}
```
---------------------------------------

# 후기

입력받은 숫자3개는 고정이고 재귀로 찾아야하는것은 20이 넘을수 있게 해주는

연산자다. 즉, 연산자들을 순회하며 연산자 2개를 사용했을때 20이 넘을땐 카운팅

넘지않으면 포기하고 ^ 연산자도 마찬가지로 바로 포기한다.
