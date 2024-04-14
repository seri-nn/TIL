## Lecture 07. 반복 실행을 명령하는 반복문 

### while문에 의한 문장의 반복 

#### 반복문이란?
반복문 : 하나 이상의 문장을 두 번 이상 반복 실행하기 위해서 구성하는 문장 

반복문의 종류 : while문, do~while문, for문 

#### while문에 의한 문장의 반복 
e.g.
```
#include<stdio.h>
int main(void)
{
    int num = 0;
    while (num < 5)  // 5회 반복 
    {
        printf("hello, world %d\n", &num);
        num++;
    }
    return 0;
}
```

while{}

- 중괄호 내부가 반복 영역 (들여쓰기 안해도 오류는 안 생기지만 가독성을 위해) 
- 변수 num : 반복 횟수를 조절하기 위함
- num++ : num의 값을 1 증가 시켜줌 (선연산 후증가)

e.g. 구구단 출력
```
# define _CRT_SECURE_NO_WARNINGS
# include<stdio.h>

int main(void)
{
    int dan = 0, num = 1;
    printf("몇 단?");
    scanf("%d", &dan);

    while(num < 10)
    {
        printf("%d x %d = %d\n", dan, num, dan*num);
        num++;  // = num = num + 1; 
    }
    return 0;
}
```
-->

몇 단? 4

4 x 1 = 4 ... 4 x 9 = 36

#### 무한 루프(Infinit Loop)의 구성
- 숫자 1은 True(참)를 의미하므로 반복문의 조건이 계속해서 True가 됨

-> 반복문의 탈출(종료) 조건이 성립하지 않는 경우를 무한 루프를 형성한다 함 

- 루프 강제 종료는 ctrl c

e.g.
```
int main(void)
{
    while(1)
    {
        printf("hello, world\n");
    }
    return 0;
}
```

#### while문의 중첩 
- while문 안에 while문
- 바깥쪽 while문 통과하고 안쪽 while문 다 돌고난 다음에 다시 바깥쪽 while문 반복

e.g. 2단부터 9단까지 출력
```
#include<stdio.h>
int main(void)
{
    int dan = 2, num = 0;

    while (dan < 10 )
    {
        num = 1;
        while (num < 10)
        {
            printf("%d x %d = %d", dan, num, dan*num);
            num++;
        }
        dan++;
        printf("\n");
    }
    return 0;
}
```

- num = 1; : 초기값 다시 설정 

-> num은 안쪽 루프 돌면서 10까지 증가한 상태니까 다음 단 출력하려면 1로 초기화 시켜줘야됨 

- dan++; : 2단, 3단 처럼 단도 1씩 증가해야됨 

### do ~ while문에 의한 문장의 반복

















