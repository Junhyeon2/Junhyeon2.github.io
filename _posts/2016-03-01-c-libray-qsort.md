---
layout: article
categories: c
title: "[C Library] qsort 함수"
tags: [C Library]
comments: true
---

C 표준 라이브러리 함수 qsort에 대해서 알아 보겠습니다.<br>
qsort 함수는 퀵 정렬 알고리즘을 손쉽게 사용하기 위해서 만들어진 함수 입니다.

## qsort 함수 원형
```
void qsort(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(const void *, const void *)
);
```
### 매개변수
- base: 정렬하려고 하는 배열의 이름(시작주소)
- num: 해당 배열의 길이
- width: 해당 배열 원소 하나의 크기(바이트)
- compare: 정렬순서를 결정하는 사용자 정의 함수

### compare 함수  팁
```
int compare(int elem1, int elem2);
int compare(int elem1, int elem2);
```
#### compare함수는 반환형 int형, 그리고 두 개의 매개변수를 필요로 합니다.
- 내림차순: elem1과 elem2를 비교, elem1이 크면 양수를 작으면 음수를 같다면 0을 반환.
- 오름차순: elem1과 elem2를 비교, elem1이 크면 음수를 작으면 양수를 같다면 0을 반환.

## 요구사항
- qsort 함수를 사용하기 위해서는 stdlib.h 헤더의 포함이 필요합니다.

## 사용 예제
<script src="https://gist.github.com/junne47/4707b803b7d381184e4c1ba8c61b01f3.js"></script>

## 실행 결과
```
9 8 7 6 5 4 3 2 1 0
```
<br>
