## Lecture 04. 데이터 표현 방식의 이해

#### 1. 입력받은 음의 정수 값을 양의 정수 값으로 바꿔서 출력하는 프로그램 작성

(단, 비트 단위 연산자를 사용해서 구현해야 하며, 양의 정수 값은 입력되지 않는다고 가정)

```
# include<stdio.h>
int main(void)
{
    int n1;
    printf("음의 정수 입력:");
    scanf_s("%d\n", &n1) 
    n1 = ~n1;  // 음수를 양수로 바꾸기 위해 -를 한 번더 해주는 것 = 1의 보수 + 1 
    n1 = n1 + 1;
    printf("변환된 양의 정수: %d\n", n1);
    return 0;
}
```

#### 2. 사용자로부터 입력받은 값의 두 배를 계산해서 출력하는 프로그램을 * 연산이 아닌, 비트 시프트 연산을 이용해서 구현

(단, 입력값은 -20^30 -1보다 크고, 2^30보다 작다고 가정)

```
# include<stdio.h>
int main(void)
{
    int n1;
    printf("정수 입력:");
    scanf_s("%d\n", &n1);
    n1 = n1 << 1;
    printf("결과값: %d\n", n1);
    return 0;
}
```
