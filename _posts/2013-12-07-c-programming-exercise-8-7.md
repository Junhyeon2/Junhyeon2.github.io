---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-7"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

년도와 월을 입력받아 마지막 날을 계산해주는 프로그램

```c
#include <stdio.h>

#define TRUE 1
#define FALSE 0

int lear_year(int y);
int last_day(int y, int m);

int main(void)
{
    int year, month, lastday;

    printf("년도를 입력하세요: ");
    scanf_s("%d", &year);

    printf("월을 입력하세요: ");
    scanf_s("%d", &month);

    lastday = last_day(year, month); //마지막날 구하기

    //결과 출력
    printf("\n%d년 %d월의 마지막 날은 %d일 입니다.\n",  
                                             year, month, lastday);
}

int leap_year(int y)  
{  
    //윤년의 조건문  
    if((y%400==0) || (y%4 == 0) && (y%100 != 0))  
        return TRUE;  
    else  
        return FALSE;  
}

int last_day(int y, int m)
{
    if(leap_year(y)) //윤년인 경우
    {
        if(m==2)
            return 29;
        else if((m==4)||(m==6)||(m==9)||(m==11))
            return 30;
        else
            return 31;
    }
    else //윤년이 아닌경우
    {
        if(m==2)
            return 28;
        else if((m==4)||(m==6)||(m==9)||(m==11))
            return 30;
        else
            return 31;
    }
}
```
