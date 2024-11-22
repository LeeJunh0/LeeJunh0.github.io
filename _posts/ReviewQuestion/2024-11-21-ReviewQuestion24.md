---
title: 기본기 복습문제24.
date: 2024-11-21 14:01:00 +0900
categories: [ReviewQuestion]  
tags:  [ C, C++ ]
---
복습문제 24번이다!

# 문제   
---------------------------------------
![DeskTop View](/assets/img/ReviewArray16.png){:w = "700" h = "400"}

---------------------------------------

# 풀이
오... 캐스팅을 해야하는 문제가 나왔다..!

```c++
int main()
{
    char arrays[3][3] = 
    {
        { 'a', 'b', 'E' },
        { 'E', '2', 'W' },
        { '3', '2', '4' }
    };

    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 3; j++)
        {
            if(97 <= arrays[i][j])
                std::cout << (char)(arrays[i][j] - 32) << " ";
            else if(65 <= arrays[i][j])
                std::cout << (char)(arrays[i][j] + 32) << " ";
            else
                std::cout << (char)(arrays[i][j] + 5) << " ";
        }

        std::cout << std::endl;
    }

    return 0;
}
```
---------------------------------------

# 후기

주의사항이 있었기 때문에 그걸 위해서라도 캐스팅을 했어야했다.

