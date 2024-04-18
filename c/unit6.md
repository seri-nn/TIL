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

#### do ~ while문의 기본 구성 

- 반복 조건을 반복문의 **마지막**에 진행하는 형태이기 때문에 **최소한 1회**는 반복 영역을 실행하게 됨

-> 1회 루프에 한해서, 조건식의 참거짓을 따지지 않고 일단 루프를 실행시킴

e.g.
```
# include<stdio.h>
int main(void)
{
    int num = 0;

    do
    {
        printf("hello world");
        num++;
    } while (num<3);
    return 0;
}
```
--> 

hello world

hello world

hello world

#### do ~ while문이 자연스러운 상황

- 최소한 1회 이상 실행되어야 하는 반복문
    - e.g. 사용자가 입력하는 수를 계속해서 더하는 프로그램

e.g.
```
# define _CRT_SECURE_NO_WARNINGS
# include<stdio.h>
int main(void)
{
    int sum = 0, num = 0;

    do
    {
        printf("정수 입력 (0 to quit):");
        scanf("%d", &num);
        sum = sum + num;
    } while(num != 0);
    printf("합계:");
    return 0;
}
```
-> 사용자가 입력하는 수를 계속 더하는 프로그램이고 0을 입력하면 합을 멈추고 합계를 출력함 

e.g. 은행 잔고를 구하는 프로그램 
```
# include<stdio.h>
int main(void)
{
    int num = 0;  // while문 사용시 초기값을 0으로 지정해놔서 false기 때문에 반복문이 실행되지 않고 종료 
    int 잔고 = 0;

    do
    {
        printf("입금하실 금액을 입력하세요 (0 to quit):");
        scanf_s("%d", &num);
        잔고 = 잔고 + num;
    } while(num!=0);
    printf("은행 잔고: %d\n", 잔고)
    return 0;
}
```

### for문에 의한 문장의 반복 

#### 반복문의 필수 3가지 요소
1. 반복을 위한 변수의 선언 e.g. int num = 0; 
2. 반복의 조건 검사 e.g. (num < 3)
3. 반복의 조건을 false로 만들기 위한 연산 e.g num++;

-> 이 3가지를 **한 줄**에 표시하는 것이 for문 

#### for문의 구조와 이해

for (초기식; 조건식; 증감식)

{

    반복의 대상이 되는 문장들
    
}

- while문 반복
```
int num=0;
while (num<3)
{
    printf("hi");
    num++:
}
```

- for문 반복
```
# include<stdio.h>
int main(void)
{
    int num;
    for(int num=0; num<3; num++)
        printf("hi");
}
```

- 일부 컴파일러는 초기식에서 변수 선언을 허용하지 않음
- for문의 반복 영역도 한 줄이면 중괄호 생략 가능

#### for문의 흐름 이해
1. 초기식 : 본격적으로 반복을 시작하기에 앞서 딱 한 번만 실행됨
2. 조건식 : 매 반복의 시작에 앞서 실행되며, 그 결과를 기반으로 반복 유무 결정
3. 증감식 : 매 반복 실행 후 마지막에 연산이 이루어짐 

- 필수 요소 3가지를 공란으로 두면 무한 루프가 생성됨

e.g.
```
# include<stdio.h>
int main(void)
{
    double 결과값 = 0.0;
    double 입력 = 0.0;
    int count = 0;

    for(;입력>=0.0;)
    {
        printf("입금하려는 금액을 입력하세요:");
        scanf_s("%lf", &입력);
        결과값 = 결과값 + 입력;
        count = count + 1;
    }
    printf("평균 입금 금액: %lf", 결과값/count);
    return 0;
}
```
-> 0 이하의 값을 입력하기 전까지는 반복문이 계속됨 

#### for문의 중첩
while, do~while문의 중첩과 다르지 않음 

e.g. 구구단 프로그램 출력
```
# include<stdio.h>
int main(void)
{
    int 단, num = 0;

    for ( 단=2; 단<10; 단++);
    {
        for(num=1; num<10; num++);
        {
            printf("%d x %d = %d", 단, num, 단*num);
        }
        printf("\n");
    }
    return 0;
}
``` 





