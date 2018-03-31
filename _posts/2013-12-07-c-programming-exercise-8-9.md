---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-9"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

점수를 입력하면 등수를 계산해주는 프로그램

```c
#include <stdio.h>

#define N 9

int rank(int arr[], int score);

int main(void)
{
    int c[N] = {10, 8, 7, 9, 6, 10, 9, 8, 7};
    int my_score;

    printf("점수를 입력하세요: ");
    scanf_s("%d", &my_score);

    printf("%d점은 %d등 입니다.\n", my_score, rank(c, my_score));
    return 0;
}

int rank(int arr[], int score)
{
    int i, count = 0;

    for(i=0; i<N; i++)
    {
        if(arr[i] > score)
            count++;
    }
    return count+1;
}
```
