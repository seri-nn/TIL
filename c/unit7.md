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


