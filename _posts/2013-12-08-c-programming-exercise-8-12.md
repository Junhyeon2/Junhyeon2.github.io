---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-12"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

팩토리얼 계산 프로그램

```c
#include <stdio.h>

int factorial(int n);

int main(void)
{
    int value;

    printf("n!를 구할 n을 입력하세요: ");
    scanf_s("%d", &value);

    printf("%d! = %d\n", value, factorial(value));
}

//팩토리얼을 구하는 재귀 함수
int factorial(int n)
{
    if(n == 1)
         return 1;
    else
        return n * factorial(n-1);
}
```
