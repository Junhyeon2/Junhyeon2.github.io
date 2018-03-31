---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-6"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

가장 낮은 어는점을 출력하는 프로그램

```c
#include <stdio.h>
#define SIZE 5

int find_min(int arr[]);
void print_arr(int arr[]);
int find_min_index(int arr[], int m);  

int main()
{
    int f[SIZE] = {3, 0, -30, -20, -1};
    int min, index;

    min = find_min(f); // 최소값 구하기
    index = find_min_index(f, min); //최소값의 첨자 구하기

    printf("어는 점 목록:");
    print_arr(f); // 배열 내용 출력하기

    // 최소값 출력하기
    printf("\n가장 낮은 어는 점: f[%d] = %d \n", index, min);

    return 0;
}
int find_min(int arr[]) // 배열의 최소값을 구하는 함수
{
    int i, min;

    min = arr[0];
    for (i=1; i<SIZE; i++)
    {
        if (arr[i] < min)
            min = arr[i];
    }
    return min;
}

void print_arr(int arr[]) // 배열 원소 출력 함수
{
    int i;
    for (i=0; i<SIZE; i++)
        printf("%4d", arr[i]);
}

//최소값의 첨자를 찾는 함수
int find_min_index(int arr[], int m)
{
    int i, s=0;

    for(i=0; i<SIZE; i++)
    {
        if(arr[i] == m) //최소값과 배열의 값이 같다면
            s = i; //배열의 첨자를 저장
    }

    return s; //배열의 첨자 반환
}
```
