---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 10-18"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

퀴즈 점수의 최고점을 출력하는 프로그램

```c
#include <stdio.h>

int index_of_max(int q[]);

int main(void)
{
    int quiz[10] = {15, 4, 8, 9, 6, 13, 12, 10, 9, 11};

    printf("퀴즈 점수 최고점은 %d점 입니다\n", quiz[index_of_max(quiz)]);

    return 0;
}

int index_of_max(int q[])
{
    int max, index, i;

    max = q[0];
    index = 0;

    for(i=1; i<10; i++)
    {
        if(max < q[i])
        {
            max = q[i];
            index = i;
        }
    }
    return index;
}
```
