---
layout: post
categories: cpp
title: "[Code Ground] 다트 게임"
tags: [Code Ground]
comments: true
---

## 문제요약
- 다트판이 원점 (0,0)을 중심으로 그려진다.
- 점수 영역(BULL, TRIPLE, DOUBLE)의 반지름을 입력받는다.
- 다트의 좌표를 입력받는다.
- 점수의 총합을 출력하라.

# 입력 조건
- 1 <= T <= 20
- 1 <= A, B, C, D, E <= 20,000
- 0 <= N <= 10,000
- -30,000 <= x, y <= 30,000
- 다트핀은 절대로 점수 구간의 경계에 꽂히지 않는다.

- 출력 조건
- 다트를 던져 얻은 총 점수를 출력.

## 문제 해결 계획
1. 입력받은 BULL, TRIPLE, DOUBLE 구간을 벡터에 저장한다.
2. 입력받은 다트의 좌표를 원점에서 좌표까지의 거리를 계산하여 BULL, TRIPLE, DOUBLE, SINGLE을 판별한다.
3. atan2함수를 이용하여 좌표의 값을 각도의 값으로 반환 받는다.
4. 이 때 반환되는 값은 파이 값으로 다음 아래 그림과 같이 나누어서 점수를 결정한다
5. BULL이 아닌경우 점수에 TRIPLE, DOUBLE, SINGLE에 해당하는 값을 곱해준다.
6. 이 과정을 N번 반복하여 다트를 던져 얻은 총점을 계산하고 출력한다.

### atan2함수의 반환 값
![atan2함수의 반환 값](/images/code-ground-dart-game.jpg)

### 검증
- 반복문 한번 수행 될때 최악의 경우 비교 연산 50회
- 반복문이 N번 수행될 때: O(N)
- 알고리즘의 시간복잡도: O(50N) -> O(N)
- 최악의 경우 테스트 케이스 마다 대략 12,300,000번 연산이 필요하다.
- 1초에 대략 1억번의 연산을 수행할 수 있으므로, 이 방법으로는 문제를 해결할 수 있다.

## 문제 풀이
<script src="https://gist.github.com/Junhyeon2/54bf29166fab7c96a9ec33911e62b166.js"></script>
