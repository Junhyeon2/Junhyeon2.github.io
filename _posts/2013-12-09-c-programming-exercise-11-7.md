---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 11-7"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

구조체 사용 예제 2

```c
#include <stdio.h>
#include <string.h>

struct employee_info
{
    char no[8];
    char name[9];
    int children;
    int pay;
};

int main(void)
{
    struct employee_info e1;

    strcpy_s(e1.no, 10, "KNU-123");
    strcpy_s(e1.name, 10, "나경대");
    e1.children = 3;
    e1.pay = 4000000;

    printf("%10s%10s%10s%6s%10s\n", "사원번호", "이름", "기본금", "자녀", "자녀수당");
    printf("==============================================\n");
    printf("%10s%10s%10d%6d%10d\n", e1.no, e1.name, e1.pay, e1.children, e1.children*100000);

    return 0;
}
```
