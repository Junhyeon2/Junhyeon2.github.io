---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 10-12"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

초를 분과 초로 환산하는 프로그램

```c
#include <stdio.h>

void compute_time(int *m, int *s);

int main(void)
{
    int min, sec;

    printf("시간을 입력하세요(sec): ");
    scanf_s("%d", &sec);

    compute_time(&min, &sec);

    printf("입력된 시간: %d분 %d초\n", min, sec);

    return 0;
}

void compute_time(int *m, int *s)
{
    *m = *s / 60;
    *s = *s % 60;
}
```
