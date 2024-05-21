## Lecture 11. 1차원 배열

### 01. 배열의 이해와 배열의 선언 및 초기화 방법

#### 배열이란 무엇인가?
배열 : 다수의 변수 선언을 용이하게 하기 위해 사용하는 것

- 배열을 이용하면 하나의 선언을 통해서 둘 이상의 변수를 선언할 수 있음
- 다수의 변수로는 할 수 없는 일을 배열을 선언하면 할 수 있음
- 1차원, 2차원 형태 상관 없이 선언할 수 있음

#### 1차원 배열 선언에 필요한 것 세 가지
배열을 이루는 요소(변수)의 자료형, 배열의 이름, 배열의 길이 

e.g.
```
int arr1[7];  // 길이가 7인 int형 1차원 배열 arr1
float arr2[10];  // 길이가 10인 float형 1차원 배열 arr2
double arr3[12];  // 길이가 12인 double형 1차원 배열 arr3
```

int arr[7];에 선언되는 메모리 

![image](https://github.com/seri-nn/TIL/assets/129299033/01457ab5-073e-4ea2-bb7f-68523bf271d2)

**int형 정수 저장을 위한 4byte 메모리 블록이 7개 존재하므로 총 28byte 할당**

#### 배열의 길이 선언은 상수만 가능 
배열의 길이를 선언할 때는 반드시 상수를 사용해야함 

#### 선언된 1차원 배열의 접근
첫 번째 배열 요소의 인덱스는 0임 (파이썬의 리스트와 똑같이 셈)

e.g.
```
arr[0]=10;  // 배열 arr의 첫 번째 요소에 10을 저장해라
```

e.g.
```
# include<stdio.h>
int main(void)
{
    int arr[5];
    int sum=0, j;

    arr[0]=10, arr[1]=20, arr[2]=30, arr[3]=40, arr[4]=50;

    for(j=0; j<5; j++)
      sum=sum+arr[j];  // 10+20+30+40+50=150

    printf("배열 요소에 저장된 값의 합: %d\n", sum);
    retrun 0;
}
``` 
--> 배열 요소에 저장된 값의 합: 150 

#### 배열 선언과 동시에 초기화하기 
- int arr1[5] = {1,2,3,4,5}; : 초기화 리스트로 초기화
- int arr2[] = {1,2,3,4,5,6,7}; : 초기화 리스트는 존재하고 배열의 길이 정보가 생략된 경우 -> 자동으로 배열의 길이 정보를 채움
- int arr3[5] = {1,2}; : 초기화 값이 부족한 경우 -> 부족한 부분은 0으로 채워짐

#### 1차원 배열의 선언, 초기화 및 접근 관련 예제 
```
# include<stdio.h>
int main(void)
{
    int arr1[5] = {1,2,3,4,5};
    int arr2[] = {1,2,3,4,5,6,7};
    int ar1len, ar2len, j;

    printf("배열 arr1의 크기: %d\n", sizeof(arr1));  // sizeof : 바이트 크기 반환해주는 함수 
    printf("배열 arr2의 크기: %d\n", sizeof(arr2));

    ar1len = sizeof(arr1) / sizeof(int);
    ar2len = sizeof(arr2) / sizeof(int);

    for (j=0; j<ar1len; j++)
        printf("%d", arr1[j]);
    printf("\n");

    for (j=0; j<ar2len; j++)
        printf("%d", arr2[j]);
    printf("\n");

    return 0;
}
```
-->

배열 arr1의 크기: 20

배열 arr2의 크기: 28

1 2 3 4 5

1 2 3 4 5 6 7

### 02. 배열을 이용한 문자열 변수의 표현

#### char형 배열의 문자열 저장과 널(Null)문자 
문자열 배열 저장 시 맨 뒤에 널 문자라 불리는 '\0'이 항상 삽입됨 (문자열의 끝 의미)

e.g.
```
# include<stdio.h>
int main(void)
{
    char str1[5] = "Good";
    char str2[] = "morning";

    printf("%s\n", str1);
    printf("%s\n", str1, str2);  // 문자열 배열을 같이 출력하고 싶으면 같이 써주면 됨 

    return 0;
}
```
--> 

Good

Good morning  

```
# include<stdio.h>
int main(void)
{
    char str[] = "Good morning!";

    printf("배열 str의 크기: %d\n", sizeof(str));
    printf("널 문자 문자형 출력: %c\n", str[13]);  // \0 널 문자 자리 
    pritnf("널 문자 정수형 출력: %d\n", str[13]);

    str[12]="?";  // 배열 str에 저장된 문자열 데이터는 변경 가능

    printf("문자열 출력: %s\n", str);

    return 0;
}
```
-->

배열 str의 크기: 14

널 문자 문자형 출력:

널 문자 정수형 출력: 0

문자열 출력: Good morning?

#### 널 문자와 공백 문자의 비교
- 널 문자를 %c를 이용해서 출력 시 아무것도 출력되지 않음 -> 공백 문자는 아님
- 널 문자의 아스키 코드 값은 0이고, 공백 문자의 아스키 코드 값은 32
- 널 문자는 모니터 출력에서 의미를 갖지 않음 = 아무것도 출력되지 않는 것

```
# incldue<stdio.h>
int main(void)
{
    char nu = "\0";
    char sp = " ";

    printf("%d %d\n", nu, sp);  // 널 문자와 공백 문자의 아스키 코드 출력 
    retunr 0;
}
```
--> 0 32 

#### scanf 함수를 이용한 문자열의 입력 
- 서식문자 %s 사용
- 배열 이름 앞에는 **& 연산자 붙이지 않음**

e.g.
```
# deifne _CRT_SECURE_NO_WARNINGS
# include<stdio.h>

int main(void)
{
    char str[50];
    int idx=0;

    printf("문자열 입력:");
    scanf("%s", str);
    printf("입력 받은 문자열: %s\n", str);

    printf("문자 단위 출력:");
    while(str[idx] != "\0")  // 입력 받은 문자열의 끝에도 널 문자가 존재하는지 확인하기 위해 
    {
        printf("%c", str[idx]);
        idx++;
    }
    printf("\n");
    return 0;
}
```
--> 

문자열 입력: simple

입력 받은 문자열: simple

문자 단위 출력: simple 

- char arr1[] = {'h', 'e', 'l', 'l', 'o'}; -> 문자 배열 
- char arr2[] = {'h', 'e', 'l', 'l', 'o', '\0'}; -> 문자열 

**--> 널 문자의 존재 여부는 문자열 판단 여부** 

#### 문자열의 끝에 널 문자가 필요한 이유
- 문자열의 시작은 판단할 수 있어도 문자열의 끝은 판단이 불가함 -> 널 문자 삽입 이유

e.g.
```
# include<stdio.h>
int main(void)
{
    char str[50] = "I like C programming";
    printf("string: %s\n", str);

    str[8] = '\0';  // 8번 인덱스에 널 문자 추가 = 8번 인덱스까지만 출력 (널 문자는 끝을 의미하니까) 
    printf("string: %s\n", str);

    str[6] = '\0';
    printf("string: %s\n", str);

    return 0;
}
```
-->

string: I like C programming

string: I like C

string: I like 

#### scanf 함수의 문자열 입력 특성 
- scanf 함수는 공백을 기준으로 데이터의 수를 구분함 = 공백을 포함하는 문자열을 한 번의 scanf 함수 호출로 읽어들이지 못함

e.g.
```
# define _CRT_SECURE_NO_WARNINGS
# include<stdio.h>

int main(void)
{
    char str[50];
    int idx=0;

    printf("문자열 입력:");
    scanf("%s", str);
    printf("입력 받은 문자열: %s\n", str);  // 공백이 포함되어 있기 때문에 첫 글자만 출력됨 

    printf("문자 단위 출력:");
    while(str[idx]!='\0')
    {
        printf("%c", str[idx]);
        idx++;
    }
    printf("\n");
    return 0;
}
```
-->

문자열 입력: He is my friend

입력 받은 문자열: He

문자 단위 출력: He 










