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
















