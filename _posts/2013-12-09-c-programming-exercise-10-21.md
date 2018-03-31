---
layout: post
categories: c
title: "[C (IT COOKBOOK)] 연습문제 10-21"
tags: [새내기를 위한 첫 C언어 책]
comments: true
---

마우스 커서 이동 프로그램

```c
#include <stdio.h>
#include <string.h>
#include <windows.h>

void gotoxy(int x, int y);

int main(void)
{
    char *msg = "Happy Birthday! ";
    int repeat, i, offset=0;

    for(repeat=0; repeat<strlen(msg); repeat++)
    {
        gotoxy(10, 5);
        printf("%s", msg+offset);

        for(i=0; i<offset ;i++)
        {
            printf("%c", *(msg+i));
        }
        offset++;
        Sleep(500);
    }
}
void gotoxy(int x, int y)
{
    COORD Pos = { x-1, y-1 };
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), Pos);
}
```
