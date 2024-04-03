## Lecture 05. 상수와 기본 자료형

### - C언어가 제공하는 기본 자료형의 이해

#### 선언할 변수의 특징을 나타내기 위한 키워드 : 자료형 (Data type)
변수 이름 이외에 메모리 공간 할당에 있어 필요한 정보 

- **정수를 저장할 것인지? 실수를 저장할 것인지?**

  값을 저장하는 방식이 정수인지, 실수인지에 따라서 달라지기 때문에 용도를 결정해야함
  
- **얼마나 큰 수를 저장할 것인지?**

  큰 수를 표현하기 위해서는 많은 수의 바이트(Byte)가 필요함

  e.g. 정수 저장, 크기는 4바이트, 변수 이름은 num --> int num;

#### 기본 자료형의 종류와 데이터의 표현 범위
- **기본 자료형(Primitive Data Types)** : C언어가 기본적으로 제공하는 여러 가지 형태의 자료형

![image](https://github.com/seri-nn/TIL/assets/129299033/229ffefb-b27b-49d1-86a7-24d68b8f7b3b)

  char ->  1바이트 = 8비트 = 2^8 = 256 -> -128 ~ +127 까지 표현 
  
  크게 정수형과 실수형으로 나누고 표현하고자 하는 값의 크기에 따라서 자료형을 적절히 선택

  자료형의 바이트 수가 커지면 표현할 수 있는 데이터의 범위도 커짐

  long double은 시스템 및 컴파일러에 따라서 할당되는 메모리의 크기나 표현 가능한 데이터의 범위가 유동적인 자료형 

- **여러 자료형을 제공하고 있는 이유**
  - 데이터의 표현 방식이 다르기 때문
  - 메모리 공간을 적절히 사용하기 위해 

    e.g. 3.14라는 실수를 메모리 공간에 담길 원할 때 3.14는 4바이트 float형 변수로 충분히 표현 가능한데 8바이트 double형 변수에 저장하면 공간을 낭비하게 됨 

#### sizeof를 이용한 바이트 크기 확인
- **sizeof()** : 단항 연산자로 피연산자의 메모리 크기 반환 (피연산자로는 변수, 상수, 자료형의 이름 정도가 올 수 있음)

  - 자료형의 크기(몇 비트인지)를 알려주는 연산자 = 자료형에 따른 크기는 항상 일정??
  
e.g.
```
# include<stdio.h>
int main(void)
{
    char ch = 4;
    short sh = 1;
    int a = 2;
    long b = 5;
    long long c = 3;

    float n1 = 3.14;
    double n2 = 6.28;
    long double n3 = 1.14;

    printf("char : %d\n", sizeof(ch));
    printf("sh : %d\n", sizeof(sh));
    printf("int : %d\n", sizeof(a));
    printf("long : %d\n", sizeof(b));
    printf("long long : %d\n", sizeof(c));

    printf("float : %d\n", sizeof(n1));
    printf("double : %d\n", sizeof(n2));
    printf("long double : %d\n", sizeof(n3));

    return 0;
}
```
-> 

char : 1 

short : 2 

int : 4

long : 4

long long : 8

float : 4

double : 8

long double : 8 

#### 정수의 표현 및 처리를 위한 일반적 자료형 선택 
**일반적인 선택 = int** : CPU가 처리하기에 가장 적합한 자료형이라 연산 속도가 빠름 

**연산이 동반되면 int형으로 변환**되어 연산이 진행되기 때문에 연산을 동반하는 변수의 선언을 위해서는 int로 선언하는 것이 적합 

그렇다고 **char형, short형 변수가 불필요한 것은 아님**

최소한의 연산만 요구하거나 연산을 동반하지 않으며 많은 수의 데이터를 저장해야 한다면 사용해야함 

e.g.
```
# include<stdio.h>
int main(void)
{
    char n1 = 1, n2 = 2, r1 = 0;
    short n3 = 100, 54 = 200, r2 = 0;

    printf("char : %d byte\n", sizeof(n1)); 
    printf("short : %d byte\n", sizeof(n3)); 

    printf("char add : %d\n", sizeof(n1+n2));  
    printf("short add : %d\n", sizeof(n3+n4));

    r1 = n1 + n2;
    r2 = n3 + n4;
    printf("r1 & r2 : %d\n", sizeof(r1), sizeof(r2));  
    return 0;
}
```
->

char : 1byte  // 자료형 크기 그대로

short : 2byte

char add : 4  // 연산 진행되면서 int형으로 바뀌고 4바이트 됨 

short add : 4

r1 & r2 : 1, 2  // 연산이 진행되고 난 후의 크기니까 원래 r1, r2 자료형에 따른 바이트

#### 실수의 표현 및 처리를 위한 일반적 자료형 선택
- 실수 자료형의 선택 기준 : 정밀도 

  8바이트 크기의 **double**이 float보다 **더 정밀하게** 실수 표현 

- **일반적인 선택 : double** 

  double형 변수의 **출력** 서식 문자 : %f -> printf 일때 

  double형 변수의 **입력** 서식 문자 : %lf (long floating point number) -> scanf_s일때
  
![image](https://github.com/seri-nn/TIL/assets/129299033/a671efc4-d60b-4a78-9c55-48daab0b87b0)

e.g.
```
# include<stdio.h>
int main(void)
{
    double 반지름;
    double 넓이;

    printf("반지름을 입력하세요:");
    scanf_s("%lf", &반지름);

    넓이 = 3.1415 * 반지름 * 반지름;
    printf("넓이 : %f", 넓이);
    return 0;
}
``` 

#### unsigned를 붙여서 0과 양의 정수만 표현 
MSB(Most Significant Bit) : 가장 왼쪽에 위치한 비트로 부호를 나타내는 비트 

![image](https://github.com/seri-nn/TIL/assets/129299033/b4bd8f16-25d1-4472-b69e-bd5f10f489d7)

### - 문자의 표현 방식과 문자를 위한 자료형 

- **ASCII코드** : 컴퓨터는 문자를 표현하거나 저장하지 못해 **문자 표현을 목적으로 각 문자에 고유한 숫자 지정** 즉, 숫자를 문자에 연결한 128개의 문자

  - **작은 따옴표**로 묶어서 표현

  - 모든 아스키 코드는 1바이트로 표현 가능하기에 **char형 변수에 저장** (int형 변수에도 가능하긴함)

  - **%c** 통해서 해당 숫자의 **아스키 코드 출력** 가능

![image](https://github.com/seri-nn/TIL/assets/129299033/7bf68d1f-e03b-4e12-8685-be9e1cd58c39)

e.g.
```
# include<stdio.h>
int main(void)
{
    char ch1 = 'A';
    char ch2 = 65;
    char ch3 = 'Z';
    char ch4 = 90;

    printf("%c %d\n", ch1, ch1);
    printf("%c %d\n", ch2, ch2);
    printf("%c %d\n", ch3, ch3);
    printf("%c %d\n", ch4, ch4);
    return 0;
}
```
-> 
 
A 65 // %c는 아스키 코드 출력, %d는 해당 아스키 코드의 정수형 숫자 출력 

A 65

Z 90

Z 90 

#### 바이트 값 측정
- **%d**로 바이트 값 측정 (바이트 값은 정수로 표현되니까) 

e.g.
```
# include<stdio.h>
int main(void)
{
    printf("%d\n", sizeof(30));
    printf("%d\n", sizeof(4.01));
    printf("%d\n", sizeof('A'));
    return 0;
}
```
->

4 // int형이라?

8 // double형

4 // int형? 정수라?
  
### - 상수에 대한 이해

#### 이름을 지니지 않는 리터럴(Literal)상수
- 리터럴 상수 : 변수와 달리 이름이 없는 상수로 변경이 불가능한 상수 

  리터럴 상수도 자료형이 결정되어야 메모리 공간에 저장될 수 있음

e.g.
```
# include<stdio.h>
int main(void)
{
    printf("literal int size : %d\n", sizeof(7));
    printf("literal double size : %d\n", sizeof(7.14));
    printf("literal char size : %d\n", sizeof('A'));
    return 0;
}
```
->

literal int size : 4 // 정수는 기본적으로 int형으로 표현 

literal double size : 8 // 실수는 기본적으로 double형으로 

literal char size : 4 // 문자는 기본적으로 int형으로 

#### 접미사를 이용한 다양한 상수의 표현
- 정수형 상수의 표현을 위한 접미사

![image](https://github.com/seri-nn/TIL/assets/129299033/92e6e9a9-d30e-4cb4-b6cf-9c0b00c0287f)

- 실수형 상수의 표현을 위한 접미사

![image](https://github.com/seri-nn/TIL/assets/129299033/be2d70ed-6eb8-4897-84a1-1eece52fd374)

e.g.
```
# include<stdio.h>
int main(void)
{
    float n1 = 5.78;
    float n2 = 3.24 + 5.12;
    return 0;
}
```
-> "double"에서 "float"로 잘립니다 

n1, n2는 double(8비트)에 저장되는 값들인데 float(4비트)에 저장하려해서 데이터 손실 발생 

```
int main(void)
{
    float n1 = 5.78f;
    float n2 = 3.24f + 5.12F;
    return 0;
}
```
-> 실수 뒤에 F/f 붙여주면 오류 발생 x (대소문자 상관 없음)

#### 이름을 지니는 심볼릭 상수(Symbolic Constants)
- **심볼릭 상수** : 이름을 지니는 상수  
  - const 키워드 이용
  - 매크로 이용 

e.g.
```
# include<stdio.h>
int main(void)
{
    const int max = 100; 
    printf("%d\n", max);

    max = 200;
    printf("%d\n", max);
    return 0;
}
```
-> 

100 // max는 'max'라는 이름을 가진 상수라 값을 변경 할 수 없음 

오류 발생 // 값을 변경할 수 없는데 200으로 초기화하려 했으니 오류 발생 

### - 자료형의 변환 
#### 자동 형 변환
- 정수 -> 실수 : 3은 3.0으로 데이터 손실 없이 자동 형 변환
- 실수 -> 정수 : 소수점 이하의 값 소멸
- 큰 정수 -> 작은 정수 : 작은 정수의 크기에 맞춰서 상위 바이트 소멸
    
e.g.
```
#incldue <stdio.h>
int main(void)
{
    double n1 = 245; // 자동으로 245가 실수형으로 바뀌는 것 
    int n2 = 3.14;
    int n3 = 129;
    char ch = n3;

    printf("정수 245를 실수로 : %f\n", n1);
    printf("실수 3.14를 정수로 : %d\n", n2);
    printf("큰 정수 129를 작은 정수로 : %d\n", ch);
    retur 0;
}
```
->

정수 245를 실수로 : 245.000000

실수 3.14를 정수로 : 3

큰 정수 129를 작은 정수로 : -127 

- 정수의 승격에 의해
  char, short와 같은 정수형 데이터 연산은 int형 데이터로 자동 형 변환된 다음에 이뤄짐

- 피연산자의 자료형 불일치로 발생하는 자동 형 변환

![image](https://github.com/seri-nn/TIL/assets/129299033/f7bde086-c15a-4652-a53a-18bbab4987f3)

e.g.
```
int main(void)
{
    double n1 = 5.15 + 19;
}
```
-> 자동 형 변환 규칙에 의해 int형 데이터 19가 double형 데이터 19.0으로 형 변환 돼 덧셈 진행 

#### 명시적 형 변환 : 강제로 일으키는 형 변환 
```
# include<stdio.h>
int main(void)
{
    int n1 = 3, n2 = 4;
    double divResult;
    divResult = n1 / n2; // n1과 n2가 정수기 때문에 몫만 반환되는 정수형 나눗셈 진행 

    divResult = (double)n1 / n2; // n1이 double형으로 명시적 형 변환 발생 

    printf("나눗셈 결과: %f\n", divResult);
    return 0;
}
```
->

0.75

n1이 double형으로 형 변환되고, n1과 n2의 연산 과정에서 산술적 자동 형 변환 발생 = 실수형 나눗셈 진행 





