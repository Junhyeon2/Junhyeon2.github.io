---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 10-19"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

학생 정보를 출력하는 프로그램

```c
#include <stdio.h>
#include <string.h>

#define PERSON 10

int search(char w[], char *n[]);

int main(void)
{
    char *name[PERSON] = {"나태희", "유현빈", "나원빈", "문건영", "소지법",  
                          "나보배", "장도건", "고수영", "이나라", "김해수"};
    char *phone[PERSON] = {"010-5528-7889", "010-5211-1472",
                           "010-1235-8765", "010-8282-8282",  
                           "010-5165-3483", "010-5232-3483",
                           "010-3452-1676", "010-5210-5463",
                           "010-5210-1234", "010-8255-8255"};
    char *grade[PERSON] = {"4.3", "4.0", "3.2", "2.7", "3.2",  
                           "4.0", "4.4", "3.7", "4.2", "3.8"};
    char who[10];
    int index;

    printf("정보를 찾고 싶은 학생의 이름을 입력하세요: ");
    //scanf_s("%s", who);
    gets_s(who, 10);

    index = search(who, name);  

    if(index == -1)
    {
        printf("%s 학생은 찾을 수 없습니다.\n", who);
    }
    else
    {
        printf("\n학생 이름: %s\n", name[index]);
        printf("전화번호: %s\n", phone[index]);
        printf("학점: %s\n", grade[index]);
    }
    return 0;
}

int search(char w[], char *n[])
{
    int i, idx = -1;

    for(i=0; i<PERSON; i++)
    {
        if(strcmp(w, *(n+i)) == 0)
             idx = i;
    }

    return idx;
}
```
