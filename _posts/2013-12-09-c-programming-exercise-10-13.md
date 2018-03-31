---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 10-13"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

sizeof 연산자 사용하는 예제

```c
#include <stdio.h>

int main(void)
{
    double ary[] = {170.5, 165.3, 157.2, 160.0, 165.7};
    int i, len = sizeof(ary)/sizeof(ary[0]);

    for(i=0; i<len; i++)
        printf("ary[%d] = %.1lf\n", i, *(ary+i));

    return 0;
}
```
