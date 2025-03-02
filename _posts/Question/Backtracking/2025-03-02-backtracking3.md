---
title: BackTracking 연습문제 3
date: 2025-03-02 18:03:00 +0900
categories: [Question]  
tags:  [ C, C++, BackTracking ]
---

백트래킹에 익숙해지기 위한 연습문제 3 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/backtracking3.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>
#include <vector>

using namespace std;

void Recursion(int cur, int sum);

string str = "";
int n;
int maxSum = 0;

vector<pair<char, int>> vec =
{
    {'a',15},{'b',20},{'c',45},{'d',22},{'e',55},{'f',16},{'g',45}
};
vector<int> visited;

int main()
{
    cin >> str;
    cin >> n;
    visited.resize(str.size());
    Recursion(0, 0);
    cout << maxSum;
    
    return 0;
}

void Recursion(int cur, int sum)
{
    if (cur == str.length() - n)
    {
        if(sum % 2 == 1)
            maxSum = max(sum, maxSum);
        
        return;
    }
    
    for (int i = 0; i < str.length(); i++)
    {
        if (visited[i] == 1)
        	continue;
        
        visited[i] = 1;
        int next = 0;
        for (int j = 0; j < vec.size(); j++)
        {
            if (str[i] != vec[j].first)
                continue;
            
            next = vec[j].second;
            break;
        }
        
        Recursion(cur + 1, sum + next);
        visited[i] = 0;
    }
}
```
---------------------------------------

# 후기

입력값 문자들을 받고, n개를 제거후 문자들의 최대값이 몇인지 출력하는 문제로

n개를 제거한 문자들의 합은 항상 홀수여야한다. 백트레킹이며 중요한건

문자열에서 n개를 뺀만큼만 합을 구하는것이고 그 합이 홀수여야 한다.

그리고 문자들의 값을 구해서 그걸 더해주면된다.
