## Lecture 17. 구조체와 사용자 정의 자료형 

### 01. 구조체란 무엇인가?
- 구조체 : 하나 이상의 변수를 그룹 지어서 새로운 자료형 정의
  - 그룹 지어진 변수들은 서로 다른 자료형이어도 상관 없음 (포인터 변수나 배열도 가능)

#### 구조체의 정의
- 구조체를 정의하면 **한 번에 두 개 이상의 정보**를 반환할 수 있음
- 기본 자료형의 변수를 묶어서 **새로운 자료형**을 만든 것 -> **사용자 정의 자료형(User-Defined Data Type)**
- **구조체 멤버** : 구조체를 이루는 변수

e.g.
```
struct point  // point라는 이름의 구조체 정의
{
    int xpos;  // point 구조체를 구성하는 멤버 
    int ypos;  // point 구조체를 구성하는 멤버 
};
```

```
struct person
{
    char name[20];
    char phonNum[20];
    int age;
};
```
-> 이름, 전화번호, 나이 정보를 person이라는 구조체 정의를 통해서 묶고 있음 

#### 구조체 변수의 선언
- 구조체 변수 선언 기본 형태 : struct type_name val_name;
- 구조체 멤버의 접근 방법 : 구제초 변수의 이름.구조체 멤버의 이름

e.g. 
```
# define _CRT_SECURE_NO_WARNINGS
# include<stdio.h>

struct person
{
    char name[20];
    char phoneNum[20];
    int age;
};
int main(void)
{
    struct person p1, p2;

    strcpy(p1.name, "솜솜이");
    strcpy(p1.phoneNum, "010-1234-5678");
    p1.age=21;

    printf("이름: %s\n", p1.name);
    printf("번호: %s\n", p1.phoneNum);
    printf("나이: %s\n", p1.age);

    return 0;
}
```
->

이름: 솜솜이

번호: 010-1234-5678

나이: 21 

#### 구조체 정의와 동시에 변수 선언하기
구조체를 정의함과 동시에 변수를 선언하는 문장은 잘 사용되지 않음 

e.g.
```
struct point
{
    int xpos;
    int ypos;
}pos1, pos2, pos3;
```

#### 구조체 변수의 초기화
초기화 방식은 배열과 유사 -> 초기화 할 데이터들을 중괄호 안에 순서대로 나열 

e.g.
```
# include<stdio.h>
struct point
{
    int xpos;
    int ypos;
};
int main(void)
{
    struct point pos={10,20};

    printf("%d %d\n", pos.xpos, pos.ypos};

    return 0;
}
```
-> 10 20 

### 02. 구조체와 배열 그리고 포인터
- 여러 개의 구조체 변수를 지정할 때 구조체 배열 선언

e.g. struct point arr[4]; -> 길이가 4인 구조체 배열의 선언 

e.g.
```
# define _CRT_SECURE_NO_WARNINGS
# include<stdio.h>

struct point
{
  int xpos;
  int ypos;
};

int main(void)
{
  struct point arr[3];

  for(int j=0; j<3; j++)
  {
    printf("점의 좌표 입력:");
    scanf("%d %d", &arr[j].xpos, &arr[j].ypos);
  }
  for(int j=0; j<3; j++)
  {
    printf("[%d %d]", arr[j].xpos, arr[j].ypos);
  }
  return 0;
}
```
->

점의 좌표 입력: 2 4 

점의 좌표 입력: 3 6

점의 좌표 입력: 8 9

[2 4] [3 6] [8 9]

#### 구조체 배열의 초기화
배열요소 각각의 초기화 값을 중괄호로 묶어서 표현 

e.g. 
```
struct person arr[3]={
  {"솜솜이", "010-1234-5678", 21}  // 첫번째 요소 초기화 
  {"홍길동", "010-1111-2222", 22}  // 두번째 요소 초기화 
  {"김이박", "010-3333-4444", 23}  // 번째 요소 초기화
}; 
```

#### 구조체 변수와 포인터
구조체에서 포인터가 사용되는 경우
  -포인터를 선언하여 구조체 변수를 가리키는 경우 
  -구조체의 멤버로 포인터 변수가 선언되는 경우 

1. 포인터를 선언하여 구조체 변수 가리키는 경우

e.g.
```
struct point pos={11,12};
struct point* pptr=&pos;  // 구조체 point의 포인터 변수 선언

(*pptr).xpos=10;  // pptr이 가리키는 구조체 변수의 멤버 xpos에 접근
(*pptr).ypps=20;  // ypos에 접근 

// 괄호를 사용하는 이유는 *연산자가 .연산자보다 우선순위가 낮아서

// -> 연산자 사용 
pptr->xpos=10;  // 위 문장과 같은 뜻 
pptr->ypos=20; 
```

e.g.
```
# include<stdio.h>

struct point
{
  int xpos;
  int ypos;
};

int main(void)
{
  struct point pos1={1,2};
  struct point* pptr=&pos1;

  pptr->xpos+=1;
  pptr->ypos+=2;
  printf("[%d %d]\n", pptr->xpos, pptr->ypos);

  return 0;
}
```
-> [2 4]


2. 구조체의 멤버로 포인터 변수가 선언되는 경우 
```
# define _CRT_SECURE_NO_WARNINGS
# include<stdio.h>

struct point
{
  int xpos;
  int ypos;
};
struct circle
{
  double radius;
  struct point* center;  // 구조체 변수의 멤버로 구조체 포인터 변수가 선언될 수 있음
};
int main(void)
{
  struct point cen={2,7};
  double rad=5.5;
  struct circle ring={rad, &cen};

  printf("원의 반지름: %g\n", ring.radius);
  printf("원의 중심 [%d, %d]\n", (ring.center)->xpos, (ring.center)->ypos);

  return 0;
}
```
-> 

원의 반지름: 5.5

원의 중심 [2,7]

#### 구조체 변수와 첫 번째 멤버의 주소 값
구조체 변수의 주소값과 구조체 변수의 첫 번째 멤버의 주소값 **일치** 











