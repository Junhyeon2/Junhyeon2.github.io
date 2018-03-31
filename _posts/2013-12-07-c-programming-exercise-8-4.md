---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-4"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

센티미터를 피트 단위로 환산해주는 프로그램

```c
#include <stdio.h>

double cm_to_feet(double value);

int main(void)
{
    double height;

    printf("당신의 키는(cm)?");
    scanf_s("%lf", &height);

    printf("키 %.1lf cm는 %.1lf feet입니다.\n", height, cm_to_feet(height));
    return 0;
}

double cm_to_feet(double value)
{
    return value/30.48;
}
```
