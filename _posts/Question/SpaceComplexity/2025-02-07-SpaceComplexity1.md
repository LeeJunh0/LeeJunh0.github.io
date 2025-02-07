---
title: 공간복잡도 연습문제 1
date: 2025-02-07 17:44:00 +0900
categories: [Question]  
tags:  [ C, C++, tree]
---

공간복잡도에 익숙해지기 위한 연습문제 1 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/spaceComplexity1.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------
![Desktop View](/assets/img/spaceComplexity1-1.png){: w="700" h="400" }
![Desktop View](/assets/img/spaceComplexity1-2.png){: w="700" h="400" }
![Desktop View](/assets/img/spaceComplexity1-3.png){: w="700" h="400" }
![Desktop View](/assets/img/spaceComplexity1-4.png){: w="700" h="400" }

```c++
#include <iostream>

int main()
{
    int input;
    std::cin >> input;
    
    if (input == 1)
        std::cout << 40;
    else if (input == 2)
        std::cout << 74;
    else if (input == 3)
        std::cout << 800;
    else
        std::cout << 16;
    
    return 0;
}
```

---------------------------------------

# 후기

바이트 패딩과 64비트 일때 포인터변수의 크기를 생각해야하는 메모리 계산 문제였다.
