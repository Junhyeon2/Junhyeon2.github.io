---
layout: article
categories: cpp
title: "[Code Ground] 숫자 골라내기"
tags: [Code Ground]
comments: true
---

## 문제 요약
- N개의 10진수가 주어졌을 때, '홀수'번 나타나는 숫자를 모두 XOR 연산을 하는 문제.
- 2, 5, 3, 3, 2, 4, 5, 3과 같이 10진수가 주어졌을 때, 3과 4를 찾아 XOR 연산의 값을 출력해야 한다.

## 입력 조건
- 1 <= T <= 20
- 0 <= N <= 3,000,000 (자연수)
- 0 <= 입력 숫자 <= 2,147,483,647  (정수)

## 출력 조건
- '홀수'번 입력받은 값들에 대해 XOR 연산한 결과를 출력.

## 문제 해결 계획
### CASE 1: '홀수'번 입력받은 수를 찾고, 그 숫자들을 XOR 연산하는 경우(완전탐색)
1. 먼저 최대 3,000,000개의 수를 입력 받는다.
2. 입력받은 수의 범위는 0과 2,147,483,647를 포함하는 사이의 정수.
3. 길이가 2,147,483,648인 배열을 만들어 입력받은 수를 카운트 한다.
4. 카운트한 결과가 홀수인 경우만 배열의 인덱스를 이용하여 XOR연산을 한다.
5. XOR연산의 결과를 출력한다.

### CASE 2: XOR연산의 특성을 이용하여 문제를 해결하는 경우
1. 먼저 최대 3,000,000개의 수를 입력 받는다.
2. 입력받은 수의 범위는 0과 2,147,483,647를 포함하는 사이의 정수.
3. XOR 연산은 '홀수'번인지 '짝수'번인지 셀 필요가 없기 때문에, 배열은 필요하지 않는다.
4. 반복문 안에서 입력받은 값을 반복적으로 XOR 연산을 진행한다.
5. XOR연산의 결과를 출력한다.

### 검증
#### CASE1: 문제를 해결할 수 없다.
```
길이가 2,147,483,648인 배열의 크기는 2,048MB가 필요하기 때문에 사용할 수 없다.
최악의 경우 N2 번 연산이 필요하다. 따라서 O(N2)이 된다. 따라서 최악의 경우 1초 안에 수행할 수 없다.
```

#### CASE2: 문제를 해결할 수 있다.
```
위의 XOR 연산 진리표를 참고하여, XOR 연산의 특성을 이해해야한다.
XOR 연산은 같은 수를 연산 했을 경우 결과 값은 0이다.
XOR 연산은 0과 어떤 수를 연산했을 경우 결과 값은 어떤 수이다.
'짝수'번 나오는 수를 모두 연산을 하면 연산 결과는 0이고,  '홀수'번 나오는 수를 모두 연산을 하면 연산 결과는 자신이 된다.
따라서 입력받은 수를 모두 XOR 연산했을 경우의 결과를 출력하면 된다.
반복문 1회에 연산이 끝나기 때문에 O(N)으로 최악의 경우에도 1초 안에 수행할 수 있다.
```

#### XOR 연산 진리표

|A|B|XOR|
|---|---|---|
|1|1|0|
|1|0|1|
|0|1|1|
|0|0|0|

## 문제 풀이
<script src="https://gist.github.com/junne47/8b39133490bd18e6dabdf9799eea6cc8.js"></script>
