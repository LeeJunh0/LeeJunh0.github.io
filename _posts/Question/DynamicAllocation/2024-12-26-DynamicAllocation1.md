---
title: 동적할당 연습문제 1
date: 2024-12-26 14:18:00 +0900
categories: [Question]  
tags:  [ C, C++, 동적할당]
---

동적할당에 익숙해지기 위한 연습문제 1 이다!

# 문제   
---------------------------------------

![Desktop View](/assets/img/DynamicAllocation1.png){: w="700" h="400" }
    
---------------------------------------

# 풀이

```c++
bool Check(char* word);
void Print();

bool isCheck[3];

int main()
{
    char* a = new char();
    char* b = new char();
    char* c = new char();	
    std::cin >> a >> b >> c;
    
    isCheck[0] = Check(a);
    isCheck[1] = Check(b);
    isCheck[2] = Check(c);
    
    Print();
    
    return 0;
}

bool Check(char* word)
{
    if (*word > 90)
        return false;
    else
        return true;
}

void Print()
{
    for (int i = 0; i < 3; i++)
    {
        if (isCheck[i] == false)
        {
            std::cout << "소문자있음";
            return;
        }
    }
    
    std::cout << "모두대문자";
}
```

---------------------------------------

# 후기

이게 동적할당을 사용한 첫 문제는 아니지만 구분하기가 어려워 아예 따로 빼서

포스팅했다.
