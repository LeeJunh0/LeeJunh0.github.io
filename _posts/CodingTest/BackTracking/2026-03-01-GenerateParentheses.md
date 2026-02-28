---
title: C++ LeetCode TOP 100 22. GenerateParentheses
date: 2026-03-01 01:20:00 +0900
categories: [ CodingTest ]  
tags:  [ C, C++, Implement ]
---

리트코드 TOP 100의 22번 문제 GenerateParentheses (괄호 생성) 이다.

# 문제   
---------------------------------------

![Desktop View](/assets/img/GenerateParentheses.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
class Solution {
public:
    vector<string> generateParenthesis(int n) {
         DFS("", 0, 0, n);
         return result;
    }

    void DFS(string str, int left, int right, int n)
    {
        if (left == n && right == n)
        {
            result.push_back(str);
            return;
        }

        if (left < right)
            return;

        if (left < n)
            DFS(str + '(', left + 1, right, n);

        if (right < n)
            DFS(str + ')', left, right + 1, n);
    }

private:
    vector<string> result;
};
```
---------------------------------------

# 후기

n개 만큼의 올바른 괄호 문자열을 전부 출력 하는 문제였다.

괄호이긴 하지만 이건 괄호를 생성하는 문제였고 장르도 백트레킹이였다.

DFS에 백트레킹을 적용시켜 풀었다.

올바른 문자열이라 하면 항상 ' ( ' 와 ' ) ' 는 n개만큼 존재하며 ' ( ' 가 항상 ' ) ' 보다 더 많거나 같아야 한다.

그 두 규칙을 갖추며 왼쪽오른쪽 사이즈가 n과 같을때 저장해주도록 풀었다.



