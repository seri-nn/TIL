## Lectur 03. 변수와 연산자 

### 변수(Variable)
변수 : 값을 저장할 수 있는 메모리 공간에 붙여진 이름 혹은 메모리 공간 자체를 의미

- 변수라는 것을 선언하면 **메모리 공간이 할당됨** -> 할당된 메모리 공간에 이름이 붙음
- 변수의 이름을 통해 할당된 메모리 공간에 접근이 가능
- **값을 저장**할 수 있고, **저장된 값을 참조**할 수도 있음
- 선언하고자 하는 변수의 **자료형이 같다면 한 줄에 동시 선언 가능**
- **변수 선언 동시에 데이터 저장** 가능 ("선언과 동시에 초기화 한다"라 표현)

e.g.
```
#include<stdio.h>
int main(void)
{
  int num;
  num = 20;
  printf("%d\n", num);
  return 0;
}
```
- int num;
  - int : 정수의 저장을 위한 메모리 공간 할당
  - num : 할당된 메모리 공간의 이름

- num = 20;
  - 변수 num에 20을 저장(대입)

- printf("%d\n", num);
  - num에 저장된 값 출력

 ### 변수의 이름을 지을 때 적용되는 규칙
 - 변수의 이름은 알파벳, 숫자, 언더바로 구성
 - 대소문자 구분
 - 숫자로 시작 불가
 - 키워드(Keywords) 변수 이름으로 사용 불가
 - 공백 포함 불가
 - 특수문자 포함 불가

### 변수의 자료형(Data Type)
- 정수형 변수
  - 정수 값의 저장을 목적으로 선언된 변수
  - char형, short형, int형, long형

- 실수형 변수
  - 실수 값의 저장을 목적으로 선언된 변수
  - float형, double형

--> 정수를 저장하는 방식과 실수를 저장하는 방식이 다르기 때문에 나눔

e.g.
```
#include<stdio.h>
int main(void)
{
    int num1 = 24;  // num1은 정수형 변수 중 int형 변수
    double num2 = 3.14;  // num2은 실수형 변수 중 double형 변수
    return 0;
}
```

예제1. 덧셈 프로그램
```
#include<stdio.h>
int main (void)
{
  int num1 = 3;
  int num2 = 4;
  int result = num1 + num2;

  printf("덧셈 결과: %d\n", result);
  printf("%d + %d = %d\n", num1, num2, result);
  printf("%d와 %d의 합은 %d입니다.\n", num1, num2, result);
  return 0;
}
```
---> 덧셈 결과: 7
     
     3 + 4 = 7

     3와 4의 합은 7입니다.

### 연산자(Operator)
- 연산자 : 연산을 수행하는 기호

  - '=' : 대입
  - '+' : 더하기 
  - '-' : 빼기
  - '*' : 곱하기
  - '/' : 나누기 
  - '%' : 나머지 값 반환

- 복합 대입 연산자

  - a = a + b <--> a += b
  - a = a -b <--> a -= b
  - a = a * b <--> a *= b
  - a = a / b <--> a /= b
  - a = % b <--> a %= b

- 증가 감소 연산자
  - ++num : 값을 1 증가 후, 나머지 진행 (**선 증가, 후 연산**)
  - num++ : 문장 먼저 진행 후, 값을 1 증가 (**선 연산, 후 증가**)
  - --num : 값을 1 감소 후, 나머지 진행 (**선 감소, 후 연산**)
  - num-- : 문장 먼저 진행 후, 값을 1 감소 (**선 연산, 후 감소**) 

e.g.
```
#include<stdio.h>
int main (void)
{
  int num1 = 12;
  int num2 = 12;
  printf("num1++ : %d\n", num1++);
  printf("num1: %d\n", num1);
  printf("++num2 : %d\n", ++num2);
  printf("num2 : %d\n", num2);
  return 0;
}
```
---> num1++: 12

     num1: 13

     ++num2: 13

     num2 : 13

```
# include<stdio.h>
int main(void)
{
  int num1 = 10;
  int num2 = (num1--) + 2;
  pritnf("num1: %d\n", num1);
  printf("num2: %d\n", num2);
  return 0;
}
```
---> num1: 9

     num2: 12 

























































ㅍ
