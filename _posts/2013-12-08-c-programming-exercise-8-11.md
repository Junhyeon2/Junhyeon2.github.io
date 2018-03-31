---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-11"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

양의 정수 n을 입력하면 거꾸로 출력하는 프로그램

```c
#include <stdio.h>

void palindrome(int n);

int main(void)
{
    int n;

    printf("양의 정수 n을 입력하면 거꾸로 출력하는 프로그램입니다. n은? ");
    scanf_s("%d", &n);

    palindrome(n);

    return 0;
}

void palindrome(int n)
{
    /* 재귀 함수로 구현
    printf("%d", n%10);

    if(n >= 10)
        palindrome(n/10); */

    //반복문으로 구현

    while(n >= 10)
    {
        printf("%d", n%10);
        n = n/10;
    }
    printf("%d\n", n);
}
```
