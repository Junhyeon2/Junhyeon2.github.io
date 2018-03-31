---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 8-8"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

통화 시간과 문자 사용량을 입력 받아 사용 요금을 계산하는 프로그램

```c
#include <stdio.h>

#define BASIS_CHARGE 10000
#define TEXT_CHARGE 20
#define TEL_CHARGE_ONE 100
#define TEL_CHARGE_TWO 80

int voice_charge(int v);
int text_charge(int t);
int print(int v, int t, int c);

int tel_minute = 0;
int serviceable_text_massage = 20;

int main(void)
{
    int used_text_message, used_tel_minute;
    int v_charge, t_charge, charge, VAT;

    printf("음성 통화 시간은?(분) ");
    scanf_s("%d", &used_tel_minute);

    printf("문자 전송 건수는? ");
    scanf_s("%d", &used_text_message);

    v_charge = voice_charge(used_tel_minute);
    t_charge = text_charge(used_text_message);


    charge = BASIS_CHARGE + v_charge + t_charge;
    VAT = charge * 0.1;

    printf("\n휴대폰 사용 요금 청구서\n");
    printf("===========================================\n");
    printf("음성 통화 시간 %d분\n", used_tel_minute);
    printf("문자 전송 건수 %d건\n", used_text_message);
    printf("-------------------------------------------\n");
    printf("기본요금%33d원\n", BASIS_CHARGE);
    printf("음성 통화료 %d분%24d원\n",used_tel_minute, v_charge);
    printf("문자 전송료 초과 %d건(20건 무료)%9d원\n",  
        (serviceable_text_massage - used_text_message < 0) ?   
        //문자 사용 20건 넘으면
        used_text_message - serviceable_text_massage : 0, t_charge);
        //사용 건수 - 20 을 반환, 넘지 않으면 0을 반환.
    printf("-------------------------------------------\n");
    printf("합계%37d원\n", charge);
    printf("부가세(10%%)%30d원\n", VAT);
    printf("===========================================\n");
    printf("이번 달 요금%29d원\n", charge+VAT);
    return 0;
}

int voice_charge(int v)
{
    int charge;  

    if(v <= 100)
        charge = v * TEL_CHARGE_ONE;
    else
        charge = (100 * TEL_CHARGE_ONE) + ((v-100) * TEL_CHARGE_TWO);

    return charge;
}
int text_charge(int t)
{
    if(t - serviceable_text_massage < 0)
        return 0;
    else
        return (t - serviceable_text_massage) * TEXT_CHARGE;
}
```
