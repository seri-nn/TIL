## Lecture 12. 포인터의 이해

### 01. 포인터란 무엇인가?

#### 주소 값의 저장을 목적으로 선언되는 포인터 변수
포인터 변수 : 정수 형태의 주소 값을 저장하는 목적으로 선언되는 것 

+) 변수 num이 저장되기 시작한 주소가 변수 num의 주소 값

![image](https://github.com/seri-nn/TIL/assets/129299033/381ca7a2-99ed-4fab-84b0-111596900cbc)

#### 포인터 변수 선언하기
포인터 변수에도 **type 존재** -> 가리키고자 하는 변수의 자료형에 따라 적절한 타입의 포인터 변수 선언 필요 

포인터 변수 선언할 때는 **'*' 연선자** 사용

e.g.
```
int main(void)
{ 
    int* a;  // a라는 이름의 int형 포인터 변수
    char* b;  // b라는 이름의 char형 포인터 변수
    double* c;  // c라는 이름의 double형 포인터 변수
}
```

#### 포인터 변수의 크기
포인터 변수의 크기는 시스템의 주소 값 크기에 따라 다름

e.g.
```
# include<stdio.h>
int main(void)
{
    int* a;
    char* b;
    double* c;

    printf("int형 포인터 변수의 크기: %d 바이트\n", sizeof(a));
    printf("char형 포인터 변수의 크기: %d 바이트\n", sizeof(b));
    printf("double형 포인터 변수의 크기: %d 바이트\n", sizeof(c));

    return 0;
}
```
->

int형 포인터 변수의 크기: 8바이트

char형 포인터 변수의 크기: 8바이트

double형 포인터 변수의 크기: 8바이트


### 02. 포인터와 관련 있는 & 연산자와 * 연산자

#### 변수의 주소 값을 반환하는 & 연산자
-& 연산자 : 변수의 주소 값 반환 
-& 연산자의 반환 값은 포인터 변수에 저장

e.g.
```
int main(void)
{
    int num=5;
    int* pnum=&num;  // &num -> 변수 num의 주소 값을 반환하라는 의미 

    return 0;
}
```

```
int main(void)
{
    int n1=5;
    double* pn1=&n1;  // type 일치x -> int* pn1=&n1 이어야 함 

    double n2=5;
    int* pn2=&n2;  // type 일치x -> double* pn2=&n2

    return 0;
}
```

#### 포인터가 가리키는 메모리를 참조하는 * 연산자
```
# include<stdio.h>
int main(void)
{
    int num=10;
    int* pnum=&num;  // pnum이 num을 가리킴
    *pnum=20;  // pnum이 가리키는 공간(변수)에 20을 저장 

    printf("%d\n", *pnum);  // pnum이 가리키는 공간(변수)에 저장된 값 출력
    return 0;
}
``` 
-> 20

- 포인터 변수 앞에 * 연산자를 붙이게 되면, 포인터 변수가 가리키는 메모리 공간에 존재하는 값을 참고하라는 의미

```
#include<stdio.h>
int main(void)
{
    int num1=100, num2=100;
    int * pnum;

    pnum=&num1;  // 포인터 pnum이 num1을 가리킴
    (*pnum)+=30;  // num1+=30;과 동일

    printf("num1: %d", num1);
    retur 0;
}
```
-> 130 

#### 다양한 포인터 형(type)이 존재하는 이유
- 포인터 형은 메모리 공간을 참조하는 방법의 힌트가 됨
- 다양한 포인터 형을 정의한 이유는 * 연산을 통한 메모리의 접근기준을 마련하기 위함 











