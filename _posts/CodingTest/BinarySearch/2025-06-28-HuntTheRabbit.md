---
title: C++ 백준 13777번 / HuntTheRabbit
date: 2025-06-28 01:20:00 +0900
categories: [ CodingTest ]  
tags:  [ C, C++, BinarySearch ]
---

백준 13777번 문제인 HuntTheRabbit 이다.

# 문제   
---------------------------------------

![Desktop View](/assets/img/HuntTheRabbit.png){: w="700" h="400" }

---------------------------------------

# 풀이

```c++
#include <iostream>

using namespace std;

int main()
{
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);
    
    int num;
    while (cin >> num)
    {
        if (num <= 0)
            break;
        
        int left = 1;
        int right = 50;		
        int mid = 0;
        
        while (left < right)
        {
            mid = (left + right) / 2;
            if (mid == num)
                break;
            
            cout << mid << ' ';
            if (mid > num)
            {
                right = mid - 1;
                continue;
            }
            
            if (mid < num)
            {
                left = mid + 1;
                continue;
            }
        }
        
        if (left == right)
            mid = left;
        
        cout << mid << ' ';
        cout << '\n';
    }
    
    return 0;
}
```
---------------------------------------

# 후기

백준에서 가장 낮은 이진탐색 문제로 1부터 50까지의 숫자중 입력받으면

해당 숫자를 찾을때 까지의 과정을 출력해주면 되는 문제다.
