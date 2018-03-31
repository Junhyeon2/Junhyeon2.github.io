---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 10-15"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

학점 환산 프로그램

```c
#include <stdio.h>

void convert(double *g, double *g2, double *s);  

int main(void)
{
    double grade, grade2, score;

    printf("학생의 학점을 입력하세요(A+ = 4.3): ");
    scanf_s("%lf", &grade);

    convert(&grade, &grade2, &score);

    printf("4.5만점의 학점으로 변환: %.1lf\n", grade2);
    printf("100만점의 점수로 변환: %.1f\n", score);

    return 0;
}

void convert(double *g, double *g2, double *s)
{
    *g2 = ((*g)*4.5)/4.3;
    *s = ((*g)*100)/4.3;
}
```
