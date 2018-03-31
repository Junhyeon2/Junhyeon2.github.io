---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 11-6"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

구조체 사용 예제 1

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

    strcpy_s(e1.no, 10, "DK1234");
    strcpy_s(e1.name, 10, "홍길동");
    e1.children = 3;
    e1.pay = 300;

    printf("%10s%10s%6s%8s\n", "사원번호", "이름", "자녀", "기본금");
    printf("%10s%10s%5d%8d\n", e1.no, e1.name, e1.children, e1.pay);

    return 0;
}
```
