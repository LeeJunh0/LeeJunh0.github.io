---
title: 버블정렬과 선택정렬!
date: 2024-11-23 19:35:00 +0900
categories: [C++]  
tags:  [ Algorithm ]
---
버블정렬은 자신과 자신의 앞을 비교하며 큰 값을 뒤로 계속 넘겨 정렬하는 

알고리즘인데 상당히 구현하기 쉬운편에 속한다.

선택정렬은 자신부터 끝까지 비교하면서 가장 작은 값을 저장해놨다가 

가장 작은 값과 자신을 스왑하면서 앞에서 부터 채워나가는 정렬이다

--------------------------------------
버블정렬 구현

```c++
int main()
{
    int arr[] = { 5, 1, 2, 6, 4, 3};
    int length = sizeof(arr) / sizeof(int);

    for(int i = length - 1; i >= 0; i--)
    {
        for(int j = 0; j < i; j++)
        {
            if(arr[j] > arr[j + 1])
            {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }

    // 과정
    // 5 1 2 6 4 3 ->
    // 1 5 2 6 4 3 ->
    // 1 2 5 6 4 3 ->
    // 1 2 5 4 6 3 ->
    // 1 2 5 4 3 6 ->

    // 1 2 4 5 3 6 ->
    // 1 2 4 3 5 6 ->
    
    // 1 2 3 4 5 6 정렬 끝
    return 0;
}
```

선택정렬 구현
```c++
int main()
{
    int arr[] = { 5,3,2,1,6,4};
    
    int curMin;
    int idx = 0;
    for (int i = 0; i < sizeof(arr) / sizeof(int); i++)
    {
        curMin = arr[i];
        idx = i;
        for (int j = i; j < sizeof(arr) / sizeof(int); j++)
        {
            if (curMin > arr[j])
            {
                curMin = arr[j];
                idx = j;
            }
        }

        int temp = arr[i];
        arr[i] = arr[idx];
        arr[idx] = temp;
    }

    // 과정
    // 5 3 2 1 6 4 -> 5와 1의 교체
    // 1 3 2 5 6 4 -> 3과 2의 교체
    // 1 2 3 5 6 4 -> 5와 4의 교체
    // 1 2 3 4 6 5 -> 6과 5의 교체

    // 1 2 3 4 5 6 정렬끝

    return 0;
}

return 0;
}
```
--------------------------------------

위에 써놓은 설명과 정렬 과정이 정확히 일치한다.

버블은 뒤로 채우지만선택은 앞에서부터 채우는걸 볼수있다.

보면 버블정렬은 상당히 많은 과정이 필요한데 선택은 그보단 빠른걸 알수있다~
