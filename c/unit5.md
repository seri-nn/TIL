## Lecture 06. printf 함수와 scanf 함수 정리하기

### 01. printf 함수

#### printf 함수는 문자열을 출력하는 함수이다
- C언어는 큰 따옴표를 사용해서 문자열 표현

#### printf 함수는 특수 문자 출력이 가능하다 
- C언어에는 특수 문자(Escape Sequence)라고 불리는 문자가 있음 -> 출력 시 특수한 문자 출력하기 위함

e.g.
- ```
  # include<stdio.h>
  {
      printf("강아지가 말했다. \"멍멍"\");  // " " 를 출력하기 위해 앞뒤로 역슬래쉬를 붙여줌
      return 0;
  }
  ```
  --> 강아지가 말했다. "멍멍"

  ![image](https://github.com/seri-nn/TIL/assets/129299033/217d3d17-8568-4558-a26e-2fd250487e04)

#### printf 함수의 서식 지정과 서식 문자들 
- printf라는 이름의 맨 끝 f는 formatted를 의미

-> 다양한 형태의 숫자를 여러 번 출력하거나, 숫자와 문자를 섞어서 출력하는 등의 출력 양식을 정할 수 있음 

![image](https://github.com/seri-nn/TIL/assets/129299033/d1d350a9-aa7f-4093-9f24-83a1e713015b)

- 자주 사용하는 서식 문자
  - %d : decimal 10진수 정수
  - %o : octa 8진수 정수
  - %x : hexa decimal 16진수 정수

- #을 삽입하면 8진수 앞에 0을, 16진수 앞에 0x가 삽입됨

e.g.
```
# incldue<stdio.h>
int main(void)
{
    int num = 13;
    printf("%d\n", num);
    printf("%o %#o\n", num, num);
    printf("%x %#x\n", num, num);  // 대소문자 구별
    return 0;
}
```
-->

13

15, 015

d, 0xd 

#### 실수의 출력을 위한 서식 문자들: %f, %e
- %f : 소수 부분이 있는 실수 표현할 때
  - **소수 6번째 자리까지 채워서** 출력
  - 소수 6번째 자리 넘어갈 시, **소수 7번째 자리에서 반올림해서** 출력 
- %e : 컴퓨터는 지수를 표현할 수 없으므로, e표기법으로 지수를 대신 표현함

![image](https://github.com/seri-nn/TIL/assets/129299033/401efa6d-810b-4f29-b835-526038084992)

e.g.
```
# incldue<stdio.h>
int main(void)
{
    printf("%f\n", 0.1234);
    printf("%f\n", 0.12345678);
    printf("%e\n", 0.1234);
    printf("%e\n", 0.12345678);
    return 0; 
}
```
--> 

0.123400

0.123457

1.234000e-001

1.234568e-001

#### 문자 출력을 위한 서식 문자 %c, %s
- %c : 단일문자 출력
  e.g. 'a', 'b', 'c'
- %s : 문자열 출력
  e.g. 'apple', 'orange'

#### 필드 폭을 지정하여 정돈된 출력 보이기
- 서식 문자 앞에 숫자 입력 = 숫자는 필드 폭 의미 = 몇 칸 띄울건지 
- 오른쪽 정렬이 기본
- 왼쪽 정렬은 숫자 앞에 - 붙이기

e.g. 문자는 왼쪽 정렬, 숫자는 오른쪽 정렬하기
``` 
# incldue<stdio.h>
int main(void)
{
    printf("%-10s %-10s\n", "이름", "예치금");
    printf("%-10s %10d\n", "솜솜이", 50000);
    pirntf("%-10s %10d\n", "조세린", 2800000);
    return 0;
}
```
-->

![image](https://github.com/seri-nn/TIL/assets/129299033/d90ae45d-a26b-4b12-8823-4c5dadde217d)

### 02. scanf 함수
- 데이터를 입력받는 scanf 함수에게는 **입력의 형식**과 **입력의 장소**에 대한 정보를 전달해야 함

#### 정수 기반의 입력 형태 정의
- %d : 10진수 정수 형태로 데이터 입력받음
- %o : 8진수 양의 정수 형태로 데이터 입력받음 
- %x : 16진수 양의 정수 형태로 데이터 입력받음

e.g.
```
# define _CRT_SECURE_NO_WARNINGS
# incldue<stdio.h>
int main(void)
{
    int n1, n2, n3;
    printf("세 개의 숫자를 입력하세요:");
    scanf("%d %o %x", &n1, &n2, &n3);  // 13 13 13 입력하지만 각각 10진수, 8진수, 16진수로 인식됨 

    printf("\n 당신이 입력한 숫자는 다음과 같습니다:");
    printf("%d %d %d\n", n1, n2, n3);  // 10진수로 변환해서 출력 
    return 0; 
}
```
-->

13 11 19 

#### 실수 기반의 입력 형태 정의
- float형 데이터 삽입을 위한 서식 문자 : %f
- double, long double형 데이터 삽입을 위한 서식 문자 : %lf

-> 

float, double, long double의 데이터 **출력** : **%f %f %lf**

float, double, long double의 데이터 **입력** : **%f %lf %lf** 

e.g.
```
# defint _CRT_SECURE_NO_WARNINGS
# include<stdio.h>
int main(void)
{
    float num1;
    double num2;
    long double num3;

    printf("실수 입력1:");
    scanf("%f", &num1); 
    printf("실수 입력2:");
    scanf("%lf", &num2); 
    printf("실수 입력3:");
    scanf("%lf", &num3);
    return 0;
}
```





