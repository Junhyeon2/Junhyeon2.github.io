---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-13"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

10진수를 2진수로 환산하는 프로그램

```c
#include <stdio.h>

void print_binary(int n);

int main(void)
{
    int n;

    printf("2진수로 표현할 정수를 입력하세요: ");
    scanf_s("%d", &n);

    print_binary(n);
    printf("\n"); //개행

    return 0;
}

void print_binary(int n)
{
    //재귀 함수로 구현
    if(n == 0 || n == 1)
    {
        printf("%d", n);
        return;
    }
    print_binary(n/2);
    printf("%d", n%2);
}
```
