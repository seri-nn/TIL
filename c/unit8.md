## Lecture 09. C언어의 핵심, 함수!

### 01. 함수를 정의하고 선언하기

#### 함수를 만드는 이유
- C언어의 핵심은 함수
- 프로그래밍을 한다는 것 = 복잡한 문제를 해결하는 것
- 문제를 main이라는 하나의 함수 안에서 해결하다 보면 복잡해지고 어려워짐
- 함수의 크기는 작을수록 좋음 

-> 구현에 필요한 기능들이 어떤 것인지 분석해서 각각 독립된 함수로 구현하고 이들을 하나의 프로그램을 완성시켜야함 

#### 함수의 입력과 출력: printf 함수도 반환을 함
- printf 함수는 출력된 문자열의 길이를 반환함

#### 함수의 구분
- 전달인자와 반환 값의 유무에 따라 4가지 유형으로 구분할 수 있음
  - 유형1: 전달인자 o, 반환 값 o
  - 유형2: 전달인자 o, 반환 값 x
  - 유형3: 전달인자 x, 반환 값 o
  - 유형4: 전달인자 x, 반환 값 x

![image](https://github.com/seri-nn/TIL/assets/129299033/cf460e32-ce5c-420a-a994-04195ad3d122)

e.g.

- 유형1
```
# include<stdio.h>

int Add(int n1, n2)
{
    return n1+n2;
}
int main(void)
{
    int result;

    result=Add(3,4);
    printf("덧셈 결과: %d\n", result);
    return 0;
}
```
--> 덧셈 결과: 7 

- 유형2
```
# include<stdio.h>

void ShowAddResult(int num)
{
    printf("덧셈 결과 출력: %d\n", num);
}
int main(void)
{
    int result;
    result=3+4;
    ShowAddResult(result);
    return 0;
}
```
--> 덧셈 결과 출력: 7

- 유형3
```
#define _CRT_SECURE_NO_WARNINGS
# include<stdio.h>

int ReanNum(void)
{
    int num;
    scanf("%d", &num);
    return num;
}
int main(void)
{
    int result;
    result=ReadNum();
    prinf("결과 출력: %d\n", result);
    return 0;
}
```
--> 

3

결과 출력: 3 

- 유형4
```
# define _CRT_SECURE_NO_WARNINGS
# include<stdio.h>

void HowToUseThisProg(void)
{
    printf("두 개의 정수를 입력하시면 덧셈 결과가 출력됩니다.\n");
    printf("두 개의 정수 입력\n");
}
int main(void)
{
    int n1, n2;
    HowToUseThisProg();
    scanf("%d %d", &n1, &n2);
    printf("덧셈 결과 출력: %d\n", n1+n2);
    return 0;
}
```
--> 

두 개의 정수를 입력하시면 덧셈 결과가 출력됩니다.

두 개의 정수 입력

3 4 

덧셈 결과 출력: 7

#### 값을 반환하지 않는 return 
- return문에는 '값의 반환'과 '함수의 탈출'이라는 두 가지 기능 존재
- 값을 반환하지 않는 형태로 return문 구성해 값은 반환하지 않되 함수를 빠져나가는 용도로 사용할 수 있음

e.g.
```
void ShowAddResult(int num)
{
    if(num<0)
      return;
}
```

#### 함수의 정의와 그에 따른 원형의 선언
- 컴파일이 위에서 아래로 진행이 되기 때문에 함수의 배치 순서 중요
- 컴파일 되지 않은 함수는 호출이 불가능함
- 이후에 등장하는 함수에 대한 정보를 컴파일러에게 제공해서 이후에 등장하는 함수의 호출 문장이 컴파일 가능하게 함
- 이렇게 제공되는 함수의 정보를 '함수의 선언'이라 함

#### 다양한 종류의 함수 정의 
- NumberCompare

e.g.
```
# include<stdio.h>

int NumberCompare(int n1, int n2);
int main(void)
{
    prinf("3과 4중 큰 수는 %d\n", NumberCompare(3,4));
    return 0;
}
int NumberCompare(int n1, int n2)
{
    if (n1>n2)
        return n1;
    else
        return n2;
}
```
--> 3과 4중에 큰 수는 4 

- AbsoCompare, GetAbsoValue

e.g.
```
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>

int AbsoCompare(int n1, int n2);
int GetAbsoValue(int num);

int main(void)
{
    int n1, n2;
    printf("두 개의 정수 입력:")
    scanf("%d %d", &n1, &n2);
    printf("절댓값이 큰 정수: %d\n", AbsoCompare(n1, n2));
    return 0;
}
int AbsoCompare(int n1, int n2);
{
    if (GetAbsoVal(n1) > GetAbsoVal(n2))
        return n1;
    else
        return n2;
}
int GetAbsoValue(int num)
{
    if (num<0)
        return num*(-1);
    esle
        return num;
}
```
--> 

두 개의 정수 입력: 5 -9

절댓값이 큰 정수: -9 


### 02. 변수의 존재 기간과 접근 범위: 지역변수

#### 함수 내에만 존재 및 접근 가능한 지역변수
- 지역변수: 함수 내에 선언되는 변수
  - 한 지역(함수) 내에 동일한 이름의 변수 선언 불가(다른 지역에는 가능)
  - 해당 지역을 빠져나가면 지역변수는 소멸
  - 호출될 때마다 새롭게 할당 

#### 다양한 형태의 지역변수
- for문의 중괄호 내에 선언된 변수도 지역변수
- 이 지역변수는 for문의 중괄호를 빠져나가면 소멸 = for문의 반복 횟수만큼 지역변수가 할당되고 소멸

- if문에서의 지역변수 확인

e.g.
```
# include<stdio.h>
int main(void)
{
    int num=1;
    if (num==1)
    { 
        int num=7;  // 주석 처리했을 때 실행 결과 
        num+=10;
        printf("if문 내 지역변수 num: %d]n", num);
    }
    printf("main 함수 내 지역변수 num: %d\n", num);
    return 0;
}
```
-> 

if문 내 지역변수 num: 17

main 함수 내 지역변수 nun: 1 

//주석처리 후 실행 결과

if문 내 지역변수 num: 11

main 함수 내 지역변수 num: 11

- 중괄호를 통해 만드는 지역변수

e.g.
```
# include<stido.h>

int main(void)
{
    int num=1;
    {  // 중괄호 시작 
        int num=7;
        num+=10;
        printf("중괄호 내 지역변수 num: %d\n", num);
    }  // 중괄호 끝 
    printf("main 함수 내 지역변수 num: %d\n", num)l
    return 0;
}
```
->

중괄호 내 지역변수 num: 17

main 함수 내 지역변수 num: 1

### 03. 전역변수, static 변수, register 변수
- 전역변수 : 함수 외부에 선언
  - 프로그램의 시작과 동시에 메모리 공간에 할당돼 종료 시까지 존재
  - 별도의 값으로 초기화하지 않으면 0으로 초기화됨
  - 프로그램 전체 영역 어디서든 접근 가능
  - 많이 쓰면 좋지 않음
  
e.g.
```
# include<stdio.h>
int num;  // 전역변수는 기본 0으로 초기화됨 

int main(void)
{
    printf("num: %d\n", num);  // 0 
    Add(3)
    printf("num: %d\n", num);  // 3 
    num++;  // 전역변수 num의 값 1 증가 
    printf("num:%d\n", num);  // 4 
    return 0;
}

void Add(int val)
{
    num+=val;  // 전역변수 num의 값 val만큼 증가 
}
```
-->

num: 0

num: 3

num: 4

```
# include<stdio.h>
int Add(int val);
int num=1;

int main(void)
{
    int num=5;
    printf("num: %d\n", Add(3));  // 9+3 
    printf("num: %d\n", num+9);  // 9+5 
    return 0;
}

int Add(int val)
{
    int num=9;
    num+=val;
    return num;
}
```
-->

num: 12

num: 14 

#### 지역변수에 static 선언을 추가한 static 변수
- static 변수의 특성 (지역, 전역변수 특성 두 개 다 가짐)
  - 지역변수 : 선언된 함수 내에서만 접근이 가능
  - 전역변수 : 딱 1회 초기화되고 프로그램 종료 시까지 메모리 공간에 존재

e.g.
```
# include<stdio.h>
void SimpleFunc(void)
{
    static int num1=0;  // 전역, 지역변수 특성 가짐 
    int num2=0;  // 지역변수 
    num1++, num2++;
    printf("static: %d, local: %d\n", num1, num2);
}
int main(void)
{
    int j;
    for(j=0; j<3; j++)
        SimpleFunc();
    return 0;
}
```
-->

static: 1, local: 1

static: 2, local: 1

static: 3, local: 1

### 04. 재귀함수에 대한 이해
- 재귀함수 : 자기 자신을 재호출하는 형태로 정의된 함수 

#### 탈출조건이 존재하는 재귀함수의 예
e.g.
```
# include<stdio.h>
void Recursive(int num)
{
    if(num<=0)  // 재귀의 탈출 조건
        return;  // 재귀의 탈출 
    printf("Recursive call %d\n", num);
    Recursive(num-1);  // 자기 자신을 재호출 
}

int main(void)
{
    Recursive(3);
    return 0;
}
```
-->

Recursive call 3

Recursive call 2

Recursive call 1


#### 재귀함수의 활용 사례 : 팩토리얼 함수
e.g.
```
# include<stdio.h>

int factorial(int);  // 함수의 원형 선언 
int main(void)
{
    for(int k=1; k<10; k++)
    {
        printf("%d!=%d\n", k, factorial(k));
    }
    return 0;
}

int factorial(int n)  // 함수의 정의 
{
    if (n==0)
        return 1;  // **주의** 
    else
        return n*factorial(n-1);
}
```

















