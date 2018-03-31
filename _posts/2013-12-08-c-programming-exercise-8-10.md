---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-10"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

득표수를 통해서 순위를 계산하는 프로그램

```c
#include <stdio.h>

#define PERSONS 30
#define STARS 6

int rank(int arr[], int score);

int main(void)
{
    int survey[PERSONS] = {1, 3, 2, 5, 3, 2, 1, 2, 3, 4, 5, 2, 3, 3,  
                        2, 1, 4, 5, 2, 3, 5, 1, 3, 4, 2, 3, 1, 4, 2, 3};
    int vote[STARS] = {0};
    char name[STARS][20] = { {""}, {"성춘향"}, {"장화"}, {"갑돌이"}, {"갑순이"}, {"이몽룡"} };
    int i, score;

    for(i=0; i<PERSONS; i++)
        vote[survey[i]]++;

    printf("%8s%10s%8s\n","연예인", "득표수", "순위");
    printf("============================\n");

    for(i=1; i<STARS; i++)
    {
        score = rank(vote, vote[i]);
        printf("%8s%10d%10d\n", name[i], vote[i], score);
    }

    return 0;
}

int rank(int arr[], int score)
{
    int i, count = 0;

    for(i=0; i<STARS; i++)
    {
        if(arr[i] > score)
            count++;
    }
    return count+1;
}
```
