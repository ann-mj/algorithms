# 알고리즘(Algorithm)

- __알고리즘 이란?__
  - 어떤 문제를 풀기 위한 절차/방법
  - 어떤 문제에 대해, 특정한 `입력`을 넣으면 원하는 `출력`을 얻을 수 있도록 만드는 프로그래밍
  - 계산 문제를 풀기 위한 도구
  - 주어진 문제를 풀기 위한 단계별 지시사항들
  - Ex. 웹 사이트를 검색할 때 특정 정보가 있는 페이지를 빨리 검색, 공개키 암호화와 전자서명 등
- __알고리즘을 분석 하는 이유__
  - `시간`과 `공간`적으로 어느 것이 가장 효율적인지 알 수 있음

# 복잡도(Complexity)

복잡도는 알고리즘의 성능을 나타내는 척도이다.

- __시간 복잡도__
  - 알고리즘을 위해 필요한 연산의 횟수
- __공간 복잡도__
  - 알고리즘을 위해 필요한 메모리의 양

## Trade-off 

시간 복잡도와 공간 복잡도는 일종의 `거래 관계(Trade-off)`가 성립한다. 예를 들면, 메모리를 더 소모하여 시간적 이점을 얻는 경우이다.

> Memoization : 메모리를 더 많이 사용하여 시간을 비약적으로 줄이는 방법

## 수행 시간 분석과 증가율

수행 시간 분석이란 `입력 데이터의 개수(N)`가 증가함에 따라 처리 시간이 얼마나 증가하는지를 분석하는 것을 의미한다.
  
## 시간 복잡도와 근사치

일반적으로 '복잡도'라고 하면 시간 복잡도를 의미한다. 시간 복잡도는 `빅오(Big-O)` 표기법을 사용한다. 빅오 표기법은 `함수의 상한만`을 나타낸다.
특히 소스 코드에서 가장 `시간적 영향력이 큰 부분(근사치)`을 빅오 표기법으로 나타낸다. 

__시간적 영향력이 큰 부분(근사치)이란, 입력 데이터 개수(N)에 비례하여 연산 횟수가 증가하는 경우를 말한다.__ 

> 시간 복잡도에서의 연산 이란 ? 
> 
> 사칙 연산 뿐만 아니라, 비교 연산 같은 기본 연산도 다 포함한다.

```java
int n = 10; // 연산 횟수 1번
for(int i=0; i<n; i++) { // 입력 데이터 n 이 100 이면 최소 100 번 연산
  // 생략
}
```

위 코드는 O(1) + O(n) 이런식으로될텐데 여기서 시간적 영향력이 가장 큰 부분이 O(n) 이고 이 값이 `근사치`가 된다.

### 빅오(Big-O) 표기법

|    빅오 표기법           | 명칭                        | 
|:--- | ---: |   
| O(1)             | 상수 시간(Constant Time)            | 
| O(logN)           | 로그 시간(Log time)            | 
| O(N)           | 선형 시간            | 
| O(NlogN)           | 로그 선형 시간          | 
| O(N^2)          | 이차 시간            | 
| O(N^3)          | 삼차 시간            |
| O(2^n)          | 지수 시간            | 

### 시간 복잡도 분석이 중요한 이유 

시간 복잡도 분석이 중요한 이유는 문제 풀이에서 주어진 `입력 데이터 개수(N)`, `탐색 범위`, `데이터의 크기`에 따라서 얼마나 효율적인 알고리즘을 작성해야하는 지 눈치 챌 수 있기 때문이다.

#### 시간 제한이 1초인 경우 

- N 의 범위가 500 인 경우 : 시간 복잡도가 O(N^3) 인 알고리즘을 설계하면 문제를 풀 수있다.
- N 의 범위가 2000 인 경우 : 시간 복잡도가 O(N^2) 인 알고리즘을 설계하면 문제를 풀 수있다.
- N 의 범위가 십만 인 경우 : 시간 복잡도가 O(NlogN) 인 알고리즘을 설계하면 문제를 풀 수있다. 
- N 의 범위가 천만 인 경우 : 시간 복잡도가 O(N) 인 알고리즘을 설계하면 문제를 풀 수있다.

## 공간 복잡도

공간 복잡도 또한 시간 복잡도 처럼 `빅오(Big-O)` 표기법을 사용한다. 시간 복잡도에서 1초라는 절대적인 제한이 있던 것 처럼, 메모리 사용량에도 제한이 있다. 보통 `MB` 단위로 제시된다.

문제에서 '시간 제한 1초, 메모리 제한 128MB' 라고 되어있는 것은 시간 복잡도와 공간 복잡도를 함께 제한하기 위하여 명시하는 것이다.

## References

> Introduction to Algorithms (Third edition)
>
> 다양한 예제로 학습하는 데이터 구조와 알고리즘 for Java