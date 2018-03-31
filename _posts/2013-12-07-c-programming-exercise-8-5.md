---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-5"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

키와 체중을 입력 받아 표준 체중과의 차이를 계산하는 프로그램

```c
#include <stdio.h>

double difference(double h, double w);

int main(void)
{
    double height, weight, std_weight, result;

    printf("키는? ");  
    scanf_s("%lf", &height);   //키를 입력받는다.
    printf("체중은? ");
    scanf_s("%lf", &weight);   //체중을 입력받는다.

    std_weight = (height - 100)*0.9;   //표준체중 구하기.
    result = difference(weight, std_weight); //difference함수 호출.

    //결과 출력
    printf("키가 %.1lf인 사람의 표준 체중 %.1lfKg", height, std_weight);

    if(result > 0)
        printf("보다 %.1lfKg 미달\n", result);
    else if(result < 0)
        printf("보다 %.1lfKg 초과\n", -result);  
        //-result를 출력해야 양수로 출력됨
    else
        printf("과 동일\n");

    return 0;

}

double difference(double w, double std_w)
{
    double dif;

    dif = std_w - w;

    if(dif > 0 && dif < 0.1) //0과 0.1사이에서는 0을 반환
        return 0;
    else  
        return dif;
}
```
