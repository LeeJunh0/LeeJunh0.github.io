---
title: 순열 알고리즘 란?
date: 2025-03-03 05:07:00 +0900
categories: [C++]  
tags:  [ Algorithm ]
---

## 순열알고리즘 ?
--------------------------------

순열은 전에 설명했으니 넘어가고 말 그대로 순열을 구하는 알고리즘이다.

순열을 구하는 방법으로는 2가지가 있다.

--------------------------------
## 1. 비재귀 형태의 스왑을 이용하는 방법
--------------------------------
중요한 점을 미리 말하자면 비재귀의 경우 좀 있다 나올 코드를 보면 알 수 있지만

사전순으로 다음순열을 구하는 것으로 정렬이 되어있지 않으면 모든 순열을 찾을 수없다.

비재귀 방법으로 구하는 순서는 4개다.

1. 끝에서부터 2개씩 검사하는데, i가 i - 1보다 큰 인덱스를 구하고 a라고 부르자.
2. 끝에서부터 a보다 큰 값을 가진 인덱스를 구하자 그리고 b라고 부르자.
3. a와 b의 인덱스 에 해당하는 값을 swap한다.
4. a부터 배열 끝까지의 값들을 전부 뒤집으면 다음 순열 완성이다.

물론 위에 말한거처럼 정렬이 되어있지 않으면 모든 순열을 뽑을수는 없다.

--------------------------------
## 비재귀 예시 코드
--------------------------------
```c++
vector<int> vec = { 1,2,3,4 };

int NextPermutation()
{
	int a = vec.size() - 1;
	while (a > 0 && vec[a] <= vec[a - 1])
		a -= 1;

	if (a <= 0) 
		return 0;

	int b = vec.size() - 1;
	while (vec[b] <= vec[a - 1]) 
		b -= 1;

	swap(vec[a - 1], vec[b]);

	reverse(vec.begin() + a, vec.end());
	return 1;
}

int main()
{
    while (true)
    {
        for (int n : vec)
            cout << n;

        cout << endl;
        
        int result = NextPermutation();
        if (result <= 0)
            break;
    }

    return 0;
}
```
--------------------------------
## 2. 백트레킹을 사용한 방법
--------------------------------
재귀는 정렬이 되어있지않아도 모든 경우의수를 탐색하기 때문에

모든 순열을 뽑아낼수 있지만 비재귀보다 메모리 사용량이 많다.

그래서 코테같은곳에서 시간초과가 뜨면 비재귀를 사용하는거같다.

--------------------------------
## 백트레킹 예시코드
--------------------------------

```c++
void Recursion(int cur);

vector<int> visited(4);
vector<int> vec = { 1,6,5,3 };
vector<int> path;

int main()
{
    Recursion(0);
    return 0;
}

void Recursion(int cur)
{
    if (cur == vec.size())
    {
        for (int n : path)
            cout << n;

        cout << endl;
        
        return;
    }
    
    for (int i = 0; i < vec.size(); i++)
    {
        if (visited[i] == 1)
            continue;
        
        visited[i] = 1;
        path.emplace_back(vec[i]);
        
        Recursion(cur + 1);
        
        path.pop_back();
        visited[i] = 0;
    }
}
```
--------------------------------
