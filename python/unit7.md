### Function (함수)

함수 def () : 무엇을 넣으면 그것이 처리되어 다시 어떤 것을 돌려주는 기능을 함 

= 입력된 매개변수를 가공하고 처리해서 반환해줌 -> 변수 값을 바꿀 때마다 함수를 새로 짤 필요가 없음

e.g. 리스트에서 짝수 구하는 함수
```python
def how_many_even(x):  # def 다음에 평소 짜는대로 함수 코드 넣으면 됨
    res = 0
    for i in x:
        if i%2==0:
            res=res+1
    return res
a=[2,4,5,6,7]
y=[1,9]
print(how_many_even(a))
print(how_many_even(y))
```
--> 

3 

0


#### 함수의 형식과 활용
- 별도의 반환 값이 없는 함수
  - 함수를 실행한 결과, 돌려줄 것이 없는 경우에는 return문 생략 가능
  - 반환 값 없이 return만 써도 됨

- 별도의 반환 값이 있는 함수
  - 함수에서 어떤 계산이나 작동을 한 후 반환할 값이 있으면 **return 반환 값** 형식으로 표현

- 반환할 값이 2개 있는 함수
  - 반환할 값이 2개면 **return 반환 값1, 반환 값2** 형식으로 표현

- retrun res가 아니라 print(res)일 때는 def에 프린트 값이 포함돼서 함수이름만 입력해도 값이 출력됨

  e.g.
```python
def func():
  res1 = 100
  res2 = 200

  return res1, res2

hap1, hap2 = 0, 0
hap1, hap2 = func()
print("func()에서 돌려준 값 ->", hap1, hap2) 
```
--> func()에서 돌려준 값 -> 100, 200

### 함수의 작업
#### 정의하기 (define) : 0개 또는 1개 이상의 매개변수를 가짐

- def와 함수 이름, 괄호 입력
- 괄호 안에는 옵션으로 매개변수 parameter를 입력할 수 있음
- 마지막으로 콜론 붙임
- 함수 이름은 변수 이름과 동일한 규칙으로 작성

#### 호출하기 (call) : 0개 또는 1개 이상의 결과 획득

- 호출 부분(print) 괄호 안의 갯수와 정의 부분(def)에서 괄호 안의 갯수가 같아야됨 

#### 매개변수에 기본값 설정
매개변수 설정시 초기값을 설정할 수 있음

e.g.
```python
def hap(a,b,c=2)
    result = a+b+c
    return result

x=hap(3,5)  # c=2라고 초기값 설정해둬서 2개만 써도 됨
print(x)
y=hap(3,5,7)  # c 값을 새로 정의해도 상관 없음 (덮어쓰기 됨)
print(y)
```
-->
10

15

+) 매개변수 개수 지정하지 않을 때 : def함수(*변수) 형태로 작성

e.g.
```python
def xx(*a)
    res=0
    for i in a:
        res+=i
    return res
a=xx(1,3,4)
b=xx(3,5,7,8)
print(a,b)
```
--> 8 28 

### 지역변수와 전역변수








 
