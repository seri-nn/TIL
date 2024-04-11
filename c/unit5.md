## Lecture 06. printf 함수와 scanf 함수 정리하기

### 01. printf 함수

#### printf 함수는 문자열을 출력하는 함수이다
- C언어는 큰 따옴표를 사용해서 문자열 표현

#### printf 함수는 특수 문자 출력이 가능하다 
- C언어에는 특수 문자(Escape Sequence)라고 불리는 문자가 있음 -> 출력 시 특수한 문자 출력하기 위함

- e.g.
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
- 컴퓨터는 지수를 표현할 수 없으므로, e표기법으로 지수를 대신 표현함




















