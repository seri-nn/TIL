### Lecture 03 연습문제

![image](https://github.com/seri-nn/TIL/assets/129299033/46f29289-903d-4f38-8a41-e167e983f026)

```
# include<stdio.h>
int main (void)
{
  int n1, n2;
  int result1, result2;

  printf("두 개의 정수 입력:");
  scanf_s("%d %d", &n1, &n2);
  result1 = n1 - n2;
  result2 = n1 * n2;
  printf("뺄셈 결과:%d\n", result1);
  printf("곱셈 결과:%d\n", result2);

  return 0;
}
```

![image](https://github.com/seri-nn/TIL/assets/129299033/cad10b0d-f14a-40f7-8291-885436d550ac)

```
# include<stdio.h>
int main(void)
{
  int n1, n2, n3;
  int result;
  printf("세 개의 숫자를 입력하세요:");
  scanf_s("%d %d %d", &n1, &n2, &n3);
  result = n1 * n2 + n3;
  printf("%d * %d + %d = %d\n", n1, n2, n3, result);

  return 0;
}
```

![image](https://github.com/seri-nn/TIL/assets/129299033/c8f7b7fb-854f-44be-af6b-16f9238667de)

```
# include<stdio.h>
int main (void)
{
  int n1;
  int result;
  printf("한 개의 숫자를 입력하세요:");
  scanf_s("%d", &n1);
  result = n1 * n1;
  printf("%d\n", result);

  return 0;
}
```

![image](https://github.com/seri-nn/TIL/assets/129299033/86aaf3d6-eadf-4238-9d94-02e7828fbaf7)

```
# include<stdio.h>
int main (void)
{
  int n1, n2;
  int result;
  printf("두 개의 숫자를 입력하세요:");
  scanf_s("%d %d", &n1, &n2);
  result = n1 % n2;
  printf("나머지: %d\n", result);

  return 0;
}
```














