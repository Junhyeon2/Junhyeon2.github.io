---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 10-17"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

상위 n개의 판매량을 출력하는 프로그램

```c
#include <stdio.h>

void top_n(int *s, int n);  

int main(void)
{
    int sales[10] = {203, 105, 302, 200, 289, 175, 130, 120, 267, 312};
    int n, i;

    printf("상위 n개의 판매량을 출력하기 위한 n입력(1~10): ");
    scanf_s("%d", &n);

    top_n(sales, n);

    for(i=0; i<n; i++)
        printf("판매량 %2d위 : %d\n", i+1, sales[i]);
}

void top_n(int *s, int n)
{
    int i, j, temp;

    for(i=0; i<n; i++)
    {
        for(j=i; j<10; j++)
        {
            if(*(s+i) < *(s+j))
            {
                temp = *(s+i);
                *(s+i) = *(s+j);
                *(s+j) = temp;
            }
        }
    }                  
}
```
