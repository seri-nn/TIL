## Lecture 05. 상수와 기본 자료형 

1. 사용자로부터 직사각형의 위치 정보를 입력받아서, 넓이를 계산하는 프로그램 작성

입력해야 할 직사각형의 위치 정보는 두 개의 x, y좌표(총 4개의 정수)가 돼야함.

첫번째로 입력되는 정보는 직사각형의 좌 하단 좌표이고, 두 번째로 입력되는 포인트 정보는 직사각형의 우 상단 좌표임. 좌 하단 좌표값이 우 상단 좌표 값보다 작다 가정

![image](https://github.com/seri-nn/TIL/assets/129299033/e34f413f-66f3-4867-9191-6e2b5e39e6ce)


```
# include<stdio.h>
int main(void)
{
    int x1, y1, x2, y2, r;
    printf("첫 번째 포인트의 x, y 좌표:");
    scanf_s("%d %d", &x1, &y1);
    printf("두 번째 포인트의 x, y 좌표:");
    scanf_s("%d %d", &x2, &y2);

    r = (x2 - x1) * (y2 - y1);
    printf("넓이 : %d\n", r);
    return 0;
}
```

2. 사용자로부터 두 개의 double형 실수를 입력받는다. 그리고 두 수의 덧셈, 뺄셈, 곱셈, 나눗셈의 결과를 출력하는 계산기 프로그램 작성

![image](https://github.com/seri-nn/TIL/assets/129299033/e58ac28a-6d18-4af5-8f4a-e32892beb8bf)

```
# include<stdio.h>
int main(void)
{
    double n1, n2;
    printf("두 수를 입력:");
    scanf_s("%lf %lf", &n1, &n2);
    printf("두 수의 덧셈: %f\n", n1 + n2);
    printf("두 수의 뺄셈: %f\n", n1 - n2);
    printf("두 수의 곱셈: %f\n", n1 * n2);
    printf("두 수의 나눗셈: %f\n", n1 / n2);
    return 0;
}
```

3. 사용자로부터 아스키 (ASCII) 코드 범위 내의 값을 하나 입력 받고 이에 해당하는 아스키 코드 문자 출력

예를 들어 사용자가 숫자 65를 입력하면 문자 A를 출력

![image](https://github.com/seri-nn/TIL/assets/129299033/8d22085a-0488-4e83-9db8-3304b8d85223)

```
# include<stdio.h>
int main(void)
{
    int n1;
    printf("숫자 입력:");
    scanf_s("%d", &n1);
    printf("아스키 문자 출력: %c\n", n1);
    return 0;
}
```

4. 사용자로부터 문자를 하나 입력받고 이에 해당하는 아스키 코드 숫자 출력

예를 들어 사용자가 문자 a를 입력하면 숫자 97 출력

![image](https://github.com/seri-nn/TIL/assets/129299033/4a3c05da-b88a-4a96-b161-1b2aa3424415)

```
# include<stdio.h>
int main(void)
{
    char ch1;
    printf("문자 입력:");
    scanf_s("\n %c", &ch1);
    printf("아스키 숫자 출력: %d\n", ch1);
    return 0;
}
```













