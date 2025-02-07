---
title: 시간복잡도 연습문제 1
date: 2025-02-07 16:48:00 +0900
categories: [Question]  
tags:  [ C, C++, tree]
---

시간복잡도에 익숙해지기 위한 연습문제 1 이다!

# 문제   
---------------------------------------
![Desktop View](/assets/img/timeComplexity1-5.png){: w="700" h="400" }

---------------------------------------

# 풀이
---------------------------------------
![Desktop View](/assets/img/timeComplexity1-1.png){: w="700" h="400" }
![Desktop View](/assets/img/timeComplexity1-2.png){: w="700" h="400" }
![Desktop View](/assets/img/timeComplexity1-3.png){: w="700" h="400" }
![Desktop View](/assets/img/timeComplexity1-4.png){: w="700" h="400" }

```c++
#include <iostream>

int main()
{
    int index;
    std::cin >> index;

    switch(index)
    {
        case 1:
            std::cout << 21;
            break;
        case 2:
            std::cout << 2;
            break;
        case 3:
            std::cout << 2;
            break;
        case 4:
            std::cout << 2;
            break;
    }

    return 0;
}
```

---------------------------------------

# 후기

입력된 문제에 맞는 점수를 출력하는 문제였다.
