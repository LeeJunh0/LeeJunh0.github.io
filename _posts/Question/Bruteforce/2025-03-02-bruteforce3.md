---
title: Brute force 연습문제 3
date: 2025-03-02 14:12:00 +0900
categories: [Question]  
tags:  [ C, C++, BruteForce]
---

완전탐색에 익숙해지기 위한 연습문제 3 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/bruteforce3.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>
#include <vector>
#include <string>

using namespace std;

void Recursion(int cur, int cnt,string word);

vector<string> str = { "BTS","SBS","BS","CBS","SES" };
string input = "";
int minCount = 99;

int main()
{
    cin >> input;
    Recursion(0, 0, "");
    cout << minCount;
    return 0;
}

void Recursion(int cur, int cnt, string word)
{
    if (input.length() < word.length())
        return;
    
    if (word == input)
    {
        if (minCount > cnt)
            minCount = cnt;
        
        return;
    }
    
    for (int i = 0; i < str.size(); i++)
        Recursion(cur + 1, cnt + 1, word + str[i]);
}
```
---------------------------------------

# 후기

백트레킹이나 BFS로도 풀수있지만 완전탐색의 개념을 좀 더 잡기위해

브루트포스 형태로 풀었고 문제는 입력된 문장이 되기 위해 사용한 단어의 수가

가장 작았을때 몇인지 출력해야하는 문제였다.

