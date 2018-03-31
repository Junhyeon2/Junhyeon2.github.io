---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 11-8,9"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

구조체 사용 예제 3

```c
#include <stdio.h>
#include <string.h>

#define N 5

struct employee_info
{
    char no[8];
    char name[9];
    int children;
    int pay;
    int extra_pay;
    int total;
};

int main(void)
{
    struct employee_info employ_arr[N];
    int i, max, index=0;

    strcpy_s(employ_arr[0].no, 10, "KNU-123");
    strcpy_s(employ_arr[0].name,10, "나경대");
    employ_arr[0].children = 3;
    employ_arr[0].pay = 4000000;
    employ_arr[0].extra_pay = 100000 * employ_arr[0].children;
    employ_arr[0].total = employ_arr[0].pay + employ_arr[0].extra_pay;

    strcpy_s(employ_arr[1].no, 10, "KNU-124");
    strcpy_s(employ_arr[1].name,10, "홍길동");
    employ_arr[1].children = 5;
    employ_arr[1].pay = 3000000;
    employ_arr[1].extra_pay = 100000 * employ_arr[1].children;
    employ_arr[1].total = employ_arr[1].pay + employ_arr[1].extra_pay;

    strcpy_s(employ_arr[2].no, 10, "KNU-125");
    strcpy_s(employ_arr[2].name,10, "나원빈");
    employ_arr[2].children = 1;
    employ_arr[2].pay = 5000000;
    employ_arr[2].extra_pay = 100000 * employ_arr[2].children;
    employ_arr[2].total = employ_arr[2].pay + employ_arr[2].extra_pay;

    strcpy_s(employ_arr[3].no, 10, "KNU-123");
    strcpy_s(employ_arr[3].name,10, "유현빈");
    employ_arr[3].children = 2;
    employ_arr[3].pay = 1000000;
    employ_arr[3].extra_pay = 100000 * employ_arr[3].children;
    employ_arr[3].total = employ_arr[3].pay + employ_arr[3].extra_pay;

    strcpy_s(employ_arr[4].no, 10, "KNU-123");
    strcpy_s(employ_arr[4].name,10, "소지법");
    employ_arr[4].children = 4;
    employ_arr[4].pay = 3000000;
    employ_arr[4].extra_pay = 100000 * employ_arr[4].children;
    employ_arr[4].total = employ_arr[4].pay + employ_arr[4].extra_pay;

    printf("%10s%10s%10s%8s%10s%12s\n", "사원번호", "이름", "기본금", "자녀", "자녀수당", "최종급여");
    printf("==============================================================\n");

    for(i=0; i<N; i++)
    {
        printf("%10s%10s%10d원%4d명%8d원%10d원\n", employ_arr[i].no, employ_arr[i].name,
                employ_arr[i].pay, employ_arr[i].children, employ_arr[i].extra_pay, employ_arr[i].total);
    }
    printf("==============================================================\n");
    max = employ_arr[0].total;

    for(i=0; i<N; i++)
    {
        if(max <employ_arr[i].total)
        {
            max = employ_arr[i].total;
            index = i;
        }
    }

    printf("\n최고 급여자: %s %d원\n", employ_arr[index].name, employ_arr[index].total);

    return 0;
}
```
