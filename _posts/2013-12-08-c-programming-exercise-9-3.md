---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 9-3"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

정적변수(static) 예제 프로그램

```c
#include <stdio.h>

void static_sum(int end);

static int sum; //정적변수 선언

int main(void)
{
    int i;

    for(i=0; i<10; i++)
        static_sum(i);

    return 0;
}

void static_sum(int end)
{
    int i, n = 0;

    //1~end+1까지의 합
    for(i=0; i<=end+1; i++)
        n+=i;

    printf("%2d번째 호출, sum = %3d + 1 ~%2d까지의 합: %3d\n", end+1, sum, end+1, sum+n);
    sum = sum + n; //출력 후에 정적변수에 저장.
}
```
