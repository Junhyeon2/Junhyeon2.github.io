---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 10-16"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

평균 계산 프로그램

```c
#include <stdio.h>

#define N 4

double compute_avg(int arr[]);

int main(void)
{
    int notebook[N] = {2507, 2232, 2009, 2890};
    int pen[N] = {4527, 5370, 4923, 6097};
    double average;

    average = compute_avg(notebook);
    printf("노트 평균 판매수:%.1lf\n", average);

    average = compute_avg(pen);
    printf("펜 평균 판매수:%.1lf\n", average);

    return 0;
}

double compute_avg(int arr[])
{
    int i, sum=0;

    for(i=0; i<N; i++)
        sum = sum + *(arr+i);

    return (double)sum/N;
}
```
