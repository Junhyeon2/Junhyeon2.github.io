---
layout: post
categories: c
title: "[C Library] pow 함수"
tags: [C Library]
comments: true
---

C 표준 라이브러리 함수 pow에 대해서 알아 보겠습니다.<br>
pow 함수는 거듭제곱의 값을 손쉽게 구하기 위해서 만들어진 함수 입니다.

## pow 함수 원형
```
double pow (double base, double exponent);
```
### 매개변수
- base:  거듭 제곱의 밑이 되는 값
- exponent: 거듭 제곱의 지수가 되는 값

## 요구사항
- pow 함수를 사용하기 위해서는 math.h 헤더의 포함이 필요합니다.

## 사용 예제
<script src="https://gist.github.com/Junhyeon2/1364289aaa5431d99cc300c5977b0d75.js"></script>

## 실행 결과
```
radius: 5
sphere volume: 523.598667
```
