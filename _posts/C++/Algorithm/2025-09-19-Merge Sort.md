---
title: 안정적인 정렬! 병합정렬 (MergeSort)
date: 2025-09-19 03:28:00 +0900
categories: [C++]  
tags:  [ Algorithm ]
---

## 병합정렬이란 ?
--------------------------------
배열을 반으로 쪼개서 나누어진 리스트를 각각 정렬하고 하나로 합치면서 정렬하는 방식의 알고리즘이다.

안정정렬에 속하고, 분할정복 알고리즘의 하나라고 한다. 시간복잡도는 O(nLogn)으로 굉장히 빠른편이다.

하지만 분할을 하는 과정에서 많은 배열들이 생성되기 때문에 메모리 사용량이 높다는 점을 주의해야한다.


## 알고리즘 핵심 순서 ?
--------------------------------
1. 배열을 재귀로 좌, 우 반반씩 나누어 준다.

2. 나누어진 배열을 또 반으로 나눠 정렬한다. 

3. 나누어진 배열의 크기가 0 or 1이 될 때까지 한다. 이유는 값이 한개남거나 없는 경우 정렬이 끝났다고 보기 때문. 


## 구현 예

```c++
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

void Merge(vector<int>& vec, int mid, int left, int right)
{
    // 각 나누어진 배열의 크기를 지정
	int leftArrCount = mid - left + 1;
	int rightArrCount = right - mid;

	vector<int> leftArr(leftArrCount), rightArr(rightArrCount);

    // 나누어진 각 배열에 값을 할당
	for (int i = 0; i < leftArrCount; i++)
		leftArr[i] = vec[left + i];

	for (int i = 0; i < rightArrCount; i++)
		rightArr[i] = vec[mid + i + 1];

    // 각 배열을 정렬
	int leftIndex = 0, rightIndex = 0, i = left;
	while (leftIndex < leftArrCount && rightIndex < rightArrCount)
	{
		if (leftArr[leftIndex] <= rightArr[rightIndex])
		{
			vec[i] = leftArr[leftIndex];
			leftIndex++;
		}
		else
		{
			vec[i] = rightArr[rightIndex];
			rightIndex++;
		}

		i++;
	}

	while (leftIndex < leftArrCount)
	{
		vec[i] = leftArr[leftIndex];
		leftIndex++;
		i++;
	}

	while (rightIndex < rightArrCount)
	{
		vec[i] = rightArr[rightIndex];
		rightIndex++;
		i++;
	}
}

void MergeSort(vector<int>& vec, int left, int right) // 재귀로 반씩 계속 나누어준다.
{
	if (left >= right)
		return;

	int mid = left + (right - left) / 2;
	MergeSort(vec, left, mid);
	MergeSort(vec, mid + 1, right);
	Merge(vec, mid, left, right);
}

int main()
{
	vector<int> vec(n);
	MergeSort(vec, 0, vec.size() - 1);
	return 0;
}
```
