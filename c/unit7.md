## Lecture 08. 조건에 따른 흐름의 분기

### 01. 조건적 실행과 흐름의 분기 
#### if문을 이용한 조건적 실행
- if문 : if(조건)
- 출력하려는 값(printf)가 한 줄이면 중괄호 생략 가능

e.g.
```
# include<stdio.h>
int main(void)
{
    int num;
    printf("정수 입력:");
    scanf_s("%d", &num);

    if(num<0)  // num이 0보다 작으면 아래 문장 실행 
        printf("입력 값 0보다 작다"\n);
    if(num==0)  // num이 0이면 아래 문장 실행 
        printf("입력 값은 0이다"\n);
    if(num>0)  // num이 0보다 크면 아래 문장 실행 
        printf("입력 값은 0보다 크다"\n);
    return 0;
}
```
--> 

정수 입력: 3

입력 값은 0보다 크다

정수 입력: -1

입력 값은 0보다 작다 

e.g. 
```
# include<stdio.h>
int main(void)
{
    int n1=22;
    int n2=15;

    if (n1>n2)
    {
        printf("n1이 n2보다 큽니다"\n);
        printf("%d > %d\n", n1, n2);
    }
    return 0;
}
```

#### if문을 이용한 계산기 프로그램
```
# include<stdio.h>
int main(void)
{
    int opt;
    double n1, n2;
    double result;

    printf("1.덧셈 2.뺄셈 3.곱셈 4.나눗셈"\n);
    printf("몇 번 선택");
    scanf_s("%d", &opt);
    printf("두 개의 실수 입력:");
    scanf_s("%lf %lf", &n1, &n2);

    if(opt==1)
        result n1+n2;
    if(opt==2)
        result n1-n2;
    if(opt==3)
        result n1*n2;
    if(opt==4)
        result n1/n2;

    printf("결과: %lf\n|, result);
    return 0;
}
```

-> 프로그램 구성상 사칙연산 중 하나만 실행이 됨 & 덧셈을 선택할지라도 총 4번의 조건문을 진행한다는 비효율성 존재

**이런 비효율성 때문에 사용되는 것이 if ~ else문** 

#### if~else문을 이용한 흐름의 분기
- if~else문 : if(조건) 조건 만족할 때 출력할 값, else 일때 출력할 값
- 출력값이 한 줄일 때는 중괄호 생략 가능

e.g.
```
# include<stdio.h>
int main(void)
{
    int n1=22;
    int n2=15;

    if(n1>n2)
        printf("n1이 n2보다 큽니다");
    else
        printf("n1이 n2보다 크지 않습니다");
    return 0;
}
```

#### if...else if...else문의 구성과 흐름
- if문 사이 어디든 얼마든지 else if 삽입 가능
- 조건2가 참일 때 조건2 if문만 실행하고 바로 출력됨 = 불필요하게 다른 if문을 거칠 필요 없음 
```
if(조건1)
{
    // 조건 1 만족 시 실행
}
else if(조건2)
{
    // 조건 2 만족 시 실행
}
else if(조건3)
{
    // 조건 3 만족 시 실행
}
else
{
    // 모두 불 만족 시 실행
}
```

#### 조건 연산자: 피연산자가 세 개인 삼항 연산자
- (조건) ? data1 : data2 : 조건이 참이면 data1 반환, 거짓이면 data2 반환

```
int n3;
if(n1>n2)
    n3=n1;
else
    n3=n2;
```
--> int n3 = (n1>n2) ? n1 :n2;

e.g.
```
# include<stdio.h>
int main(void)
{
    int num, abs;
    printf("정수 입력:");
    scanf_s("%d", &num);

    abs=(num>0) ? num : num*(-1);
    printf("절댓값: %d\n", abs);

    return 0;
}
```
--> 

정수 입력: -15

절댓값: 15 

### 02. 반복문의 생략과 탈출: continue & break 
#### break 반복문 탈출 
- break : break문은 자신을 감싸는 반복문 하나를 빠져 나감
- if문과 함께 사용 되어서 특정 조건이 만족될 때, 반복문을 빠져나가는 용도로 주로 사용됨

e.g.
```
# include<stdio.h>
int main(void)
{
    int sum=0, num=0;

    while(1)
    {
        sum=sum+num;
        if(sum>5000)
            break;  // 반복문 탈출 = 반복문 종료 // sum이 5000 넘어가면 종료  
        num++;
    }

    printf("sum: %d\n", sum);
    printf("num: %d\n", num);
    return 0;
}
```
-->

sum: 5050

num: 100 

#### continue 나머지 생략하고 반복조건 확인하러
- continue: continue문은 반복문을 빠져나가지 않음
- 다만 반복조건을 확인하러 올라갈 뿐
- 반복조건이 여전히 참이면 반복영역을 처음부터 실행하게 됨

-> continue에 해당되는 조건이면 값이 출력되지 않고 다시 조건문 실행됨

e.g.
```
# include<stdio.h>
int main(void)
{
    int num;
    printf("start");

    for (num=1; num<20; num++)
    {
        if(num%2==0 || num%3==0)  // num이 짝수이거나 3의 배수이면 continue
            continue;             // 짝수나 3의 배수이면 출력 안하고 넘어감! 
        printf("%d", num);
    }
    printf("end\n");
    return 0;
}
```
--> start 1 5 7 11 13 17 19 end

### 03. switch문에 의한 선택적 실행과 goto문
#### switch문의 구성과 기본 기능
- switch문의 구성
```
int main(void)
{
    switch(n)
    {
    case 1:  // 1일 때 출력 
        printf("A1");
        printf("A2");
        break;
    case 2:  // 2일 때 출력 
        printf("B1");
        printf("B2");
        break;
    defalut:
        printf("default");
    }
}
```

e.g.
```
# include<stdio.h>
int main(void)
{
    int num;
    printf("1이상 5이하의 정수 입력:");
    scanf_s("%d", &num);

    switch(num)
    {
    case 1:
        printf("1 one\n");
        break;
    case 2:
        printf("2 two\n");
        break;
    case 3:
        printf("3 three\n");
        break;
    case 4:
        printf("4 four\n");
        break;
    case 5:
        printf("5 five\n");
        break;
    default:
        printf("I don't know\n");
    }
    return 0;
}
```
-->

1이상 5이하의 정수 입력: 3

3 three

#### break문을 생략한 형태의 switch문 구성
- 출력값은 같고 case 레이블이 다를 때 printf문과 break문을 두 번 쓰지 않고 한 번만 쓸 수 있음
- 이때의 case 레이블은 한 줄에 같이 표시해도 됨

e.g.
```
# include<stdio.h>
int main(void)
{
    char n;
    printf("M 오전, A 오후, E 저녁\n");
    printf("입력:");
    scanf_s("%c", &n);

    switch(n)
    {
    case 'm':
    case 'M':
        printf("오전");
        break;
    case 'a':
    case 'A':
        printf("오후");
        break;
    case 'e':
    case 'E':
        printf("저녁");
        break;
    }
    return 0;
}
``` 

#### goto문의 사용법
- goto는 프로그램의 흐름을 복잡하게 만드는 단점이 있음
- 가급적 활용은 안하는게 좋음

e.g.
```
# include<stdio.h>
int main(void)
{
    int num;
    printf("자연수 입력:");
    scanf_s("%d" &num);

    if(num==1)
        goto ONE;
    else if(num==2)
        goto TWO;
    else
        goto OTHER;

ONE:
    printf("1 입력\n");
    goto END;
TWO:
    printf("2 입력\n");
    goto END;
OTHER:
    printf("3 혹은 다른 값 입력\n");
    goto END;
END:
    return 0;
}
```
-->

자연수 입력: 2

2 입력 


















