---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-1"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

배열에 특정 값이 몇개 포함되어 있는지 찾는 프로그램

```c
#include <stdio.h>
#define N 30

void print_title();
int frequency(int arr[], int value);

int main(void)
{
    int result[N] = {1, 3, 2, 5, 3, 2, 1, 2, 3, 4, 5, 2, 3, 3, 2,
                     1, 4, 5, 2, 3, 5, 1, 3, 4, 2, 3, 1, 4, 2, 3};
    int count, target;
    printf("갯수를 구하고 싶은 값은?(1~5)?");
    scanf_s("%d", &target);

    print_title();
    count = frequency(result, target);
    printf("배열에는 %d가 %d개 있습니다.\n", target, count);
    return 0;
}

void print_title()
{
    printf("===================================================\n");
    printf("배열에 특정 값이 몇개 포함되어 있는지 찾는 프로그램\n");
    printf("===================================================\n");
}
int frequency(int arr[], int value)
{
    int i, count =0;

    for(i=0; i<N; i++)
        if(arr[i] == value)
            count++;

    return count;
}
```
