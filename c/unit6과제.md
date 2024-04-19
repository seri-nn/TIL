### Lecture 07. 반복 실행을 명령하는 반복문

#### 1. (while문) 사용자로부터 숫자를 하나 입력받아서, 그 수만큼 "Hello, World!" 출력
```
# include <stdio.h>
int main(void)
{
    int num=0;

    printf("숫자 입력:");
    scanf_s("%d", &num);

    while(0<num)
    {
        printf("Hello, World!");
        num--;
    }
    return 0;
}
```

#### 2. (while문) 사용자로부터 하나의 숫자를 입력받은 다음, 그 수만큼 3의 배수를 출력하는 프로그램. 사용자로부터 5를 입력받았다면, 3 6 9 12 15를 출력

```
# include<stdio.h>
int main(void)
{
    int num=0;
    int j=1;

    printf("3의 배수의 개수:");
    scanf_s("%d", &num);

    while(j<=num)
    {
        printf("%d\n", j*3);
        j++;
    }
    return 0;
}
```

#### 3. (while문) 사용자가 입력하는 정수를 계속해서 더해 나가는 프로그램. 만약에 0이 입력되면 지금까지 입력된 정수의 덧셈 결과를 출력하고 프로그램을 종료시킴

```
# include<stdio.h>
int main(void)
{
    int num=1;  // 초기값을 1로 잡아야됨! 
    int sum=0;

    while(num!=0)
    {
        printf("정수 입력 (0 to quit):");
        scanf_s("%d", &num);
        sum=sum+num;
    }
    printf("입력된 정수의 총 합:%d", sum);
    return 0;
}
```

#### 4. (while문) 사용자로부터 입력받은 숫자에 해당하는 구구단을 출력하되, 역순으로 출력하는 프로그램

```
# include<stdio.h>
int main(void)
{
    int 단=0;
    int num=9;

    printf("역순으로 출력할 단 입력:");
    scanf_s("%d", &단);

    while(num>0)
    {
        printf("%d x %d = %d", 단, num, 단*num);
        num--;
    }
    return 0;
}
```

#### (while문) 입력된 정수의 평균을 구하는 프로그램. 먼저 입력할 정수의 개수를 입력받고 그 수만큼 정수를 입력받아서 평균값 출력. 입력받은 값은 정수지만, 평균값은 실수

```
# include<stdio.h>
int main(void)
{
    int 개수=0;
    int 입력=0;
    int sum=0;
    int j=1;

    printf("입력할 정수의 개수:");
    scanf_s("%d", &개수);

    while(j<=개수)
    {
        printf("%d번째 정수 입력:", j);
        scanf_s("%d", &입력);
        sum=sum+입력;
        j++;
    }
    printf("입력의 평균: %f", (double)sum/개수);
    return 0;
}
```

#### 6. (while문의 중첩) 사용자로부터 총 5개의 정수를 입력받아서 그 수의 합을 출력하는 프로그램. 정수는 반드시 0보다 큰 수여야함. 0이하의 수를 입력받을 경우에는 입력으로 인정하지 않고 다시 입력받도록 구현

```
#include<stdio.h>
int main(void)
{
    int 입력=0;
    int j=1;
    int sum=0;

    while(j<=5)
    {
        while(입력<=0)
        {
        printf("0보다 큰 수를 입력(%d번쨰):", j);
        scanf_s("%d", &입력);
        }
        sum=sum+입력;
        j++;
        입력=0;
    }
    printf("입력된 값의 총합: %d", sum);
    return 0;
}
```

#### (while문의 중첩) 다음과 같은 출력을 보일 수 있도록 프로그램을 작성하되 반드시 while문 중첩시켜서 구현

![image](https://github.com/seri-nn/TIL/assets/129299033/174c7fb0-e6cf-467d-8de6-350e9a53a04e)

```
# include<stdio.h>
int main(void)
{
    int j=0;
    int k=0;

    while(j<5)
    {
        while(k<j)
        {
            printf("o ");
            k++;
        }
        k=0;
        printf("*\n");
        j++;

    }
    return 0;
}
```

#### 8. (do~while문) 0과 100사이에 존재하는 짝수의 합을 계산해서 출력하는 프로그램. 출력결과는 2550이 되어야함.

```
# include<stdio.h>
int main(void)
{
    int num=0;
    int sum=0;

    do
    {
        sum=sum+(num*2);
        num++;
    } while(num<=50);

    printf("총 합: %d", sum);
    return 0;
}
```

#### 9. (for문) 두 개의 정수를 입력받아 그 사이에 존재하는 정수들의 합을 구하는 프로그램. 단, 첫 번째로 입력받은 숫자보다 두 번째로 입력받은 숫자가 더 크다는 조건 

```
# include<stdio.h>
int main(void)
{
    int n1, n2=0;
    int sum=0;

    printf("두 정수 입력:");
    scanf_s("%d %d", &n1, &n2);

    for(int j=n1; j<=n2; j++)
    {
        sum=sum+j;
    }
    printf("%d와 %d 사이의 정수의 합: %d", n1, n2, sum);
    return 0;
}
```

#### 10. (for문) Factorial을 계산하는 프로그램 작성. 사용자로부터 n이라는 수를 입력받음. 단, 이번 문제는 무한 루프로 구성

```
# include<stdio.h>
int main(void)
{
    int n=1;
    int j=1;
    int fac=1;

    for(;n>0;)
    {
        printf("Factorial 계산을 위한 정수 입력:");
        scanf_s("%d", &n);

        fac=fac*j;
        j++;
        printf("%d!=%d", n, fac);
    }
    return 0;
}
```








