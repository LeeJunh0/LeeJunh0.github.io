---
title: 람다식에 대하여
date: 2025-02-08 02:05:00 +0900
categories: [C++]  
tags:  [ 기본문법 ]
---

# 람다식 이란?

C++에서 람다식은 익명 함수 혹은 무명 함수를 정의하는 방법으로, 짧고 간결하게 함수를 만들 수 있다.

람다식은 일반적으로 한 번밖에 쓰지 않을 거 같은 함수지만? 짧은 함수 같은 걸 간단하게 표현할 때 주로 사용한다.

이렇게 쓰게 되면 코드의 가독성이 엄청 향상되고 간결해진다. 물론이지만 굉장히 긴 코드를 쓴다거나 복잡한걸

쓸 때는 람다식보단 그냥 함수로 만들어 빼 쓰는 게 맞다. 그런 방식으로 람다식을 쓰게 되면 장점이었던 것이

단점으로 바뀐다.

```c++
[//캡처](//매개변수) -> //반환타입
{
    // 함수 본문
}
```
---------------------------------

# 람다식의 구성요소

1. 캡처 리스트 : 람다식이 정의된 범위 내의 변수를 람다식 내부에서 사용할 수 있게 합니다. [] 안에 쓸 변수들을 넣으면 되는데
```c++
[=] // 외부 변수들을 값으로 넘김
[&] // 외부 변수들을 참조로 넘김
[x, &y] // x는 값으로, y는 참조로
```

2. 매개변수 리스트 : 함수와 마찬가지로 람다식이 받을 매개변수를 정의합니다.

3. 반환 타입 : 반환 타입을 명시할 수 있고, -> 기호를 사용합니다.

4. 함수 본문 : 람다식이 실행시킬 코드가 들어가는 부분입니다.

---------------------------------

## 예제

- 간단한 람다식 예제

```c++
auto sum = [](int a, int b) -> int { return a + b; }
int result = sum(3, 4); // 7
```

- 외부 변수 사용예제

```c++
int x = 10;
int y = 20;

auto sum = [x, &y](int a) -> int { return a + x + y; };
int result = sum(5); // 35
```

- 캡처 리스트 예제

```c++
int a = 1, b = 1;
auto fib = [=]() mutable{
    int temp = a;
    a = b;
    b = temp + b;
    return temp;
}

for(int i = 0; i < 5; ++i)
    std::cout << fib() << " "; // 1 1 2 3 5
```

- 인자로 람다식을 전달

```c++
int main()
{
    std::vector<int> vec = { 1, 2, 3, 4, 5 };
    std::for_each(vec.begin(), vec.end(), [](int &n) { n *= 2; });
    
    for(int n : vec)
        std::cout << n << " "; // 2 4 6 8 10

    return 0;
}
```

이런 저런식으로 람다식을 사용할수있는데 위에 설명 했듯이 함수 객체와 비교하면 

보다 간결하고 가독성이 좋고, 코드 작성과 유지보수에 용이하다.

---------------------------------
# 람다식을 사용 혹은 응용하는 라이브러리 함수들

- Sort함수(정렬)

```c++
#include <algorithm> // 헤더 선언

// std::sort의 함수 원형
template<class RandomIt>
void sort(RandomIt first, RandomIt last);

template<class RandomIt, class Compare>
void sort(RandomIt fitst, RandomIt last, Compare comp);
```

- first : 정렬을 시작할 범위의 첫 번째 요소의 이터레이터

- last : 정렬을 종료할 범위의 마지막 + 1 요소의 이터레이터

- comp : 정렬 기준을 제공하는 함수나 함수객체를 대신할 람다식


만약 비교함수(comp)가 제공되지 않으면 디폴트로 < 연산자를 사용하여 비교를

수행하고 오름차순으로 정렬한다.

---------------------------------

## 비교함수 멤버함수를 사용한 예제

```c++
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

struct Info 
{
	int val;
	bool operator < (const Info& i) const { return val > i.val; // val이 큰 원소가 앞에 오도록 정렬 }
};

int main() 
{
	vector<Info> v;
	for (int i = 1; i <= 5; i++) 
      v.push_back(Info{ i });

	sort(v.begin(), v.end());

	for (auto& i : v) 
      cout << i.val << ' '; cout << '\n'; // 5 4 3 2 1
}
```

## 비교함수 전역함수를 사용한 예제

```c++
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

bool compare(const string& a, const string& b)
{
    if (a.size() != b.size()) // 사이즈가 다르면 길이순으로 정렬
        return a.size() < b.size();

    return a > b; // 사이즈가 같으면 사전순 정렬
}

int main()
{
    vector<string> v{ "stack", "queue", "list", "set", "map" };
    sort(v.begin(), v.end(), compare);

    for (auto& i : v)
        cout << i << ' '; cout << '\n'; // set map list stack queue
}
```

## 비교함수 람다식

```c++
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main()
{
    vector<int> vec = { 4,6,1,5,7,9,3,2,8 };
    
    sort(vec.begin(), vec.end(), [] (int a, int b){
        return a < b;
    });
    
    for (int n : vec)
        cout << n << " "; // 1,2,3,4,5,6,7,8,9
    
    return 0;
}
```

그리고 sort에 람다식을 사용 할 때 디버깅 해보면 신기한걸 볼수있는데

우린 첫과 마지막의 주소를 sort에 넣어줬지만 a의 값을보면 4가 아니고 6인걸 볼수있는데

이건 sort의 정렬알고리즘이 퀵정렬과 Introsort 알고리즘이기 때문이다. 분할한 배열을 좌우 피벗을 기준으로 정렬해서

정렬과정에서 비교함수가 바뀌지않는 이상 요소가 어떻게 비교되든 정렬 결과는 동일해진다.

