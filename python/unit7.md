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
#### 지역변수 

: 한정된 지역(local)에서만 사용되는 변수 = **함수 안에서 정의 돼있는 것**

#### 전역변수

: 프로그램 전체(global)에서 사용되는 변수 = **함수 안에서 정의 돼있지 않은 것**

지역변수와 전역변수의 이름이 같은 경우 **지역변수가 우선됨**

e.g. 
```python
def func1():
    a=10  # 지역변수 
    print(a)

def func2():
    print(a)

a=20  # 전역변수 (함수에 포함 x)

func1()  # 이름이 같을 때 지역변수가 우선되므로 func1에선 10 출력
func2()  # func2에는 정의된 지역변수가 없으므로 전역변수 20 출력
```
--> 10 20 

### 예제
1. 3명의 사용자가 a,b,c가 두 숫자를 입력하고 합을 구하는 코드

```python
def hapfunc():
    num1=int(input("숫자:"))
    num2=int(input("숫자:"))
    return num1+num2
print("a number")
hap=hapfunc()
print(hap)
print("b number")
hap=hapfunc()
print(hap)
print("c number)
hap=hapfunc()
print(hap)
```

2. 문자열 하나를 입력 받아 인터넷 주소를 반환하는 make_url함수 정의

```python
def make_url(string):
    url="www." + string + ".com"
    print(url)  # 실행결과에 아무것도 받지않고 출력되므로 print가 def 안에 있다고 생각 가능 

make_url("naver")
make_url("facebook")
```
-->

www.naver.com

www.facebook.com

3. 문자열을 입력받아 각 문자들로 구성된 리스트를 반환하는 make_list함수

```python
def make_list(string):
    a=[]
    for i in string:
        a.append(i)
    print(a)

make_list("naver")
make_list("facebook")

for i in string:
    a.append(i)
return a
print(make_list("naver"))  # 위 코드와 같은 의미
```

--> 

['n','a','v','e','r']

['f','a','c','e','b','o','o','k']

4. 숫자로 구성된 하나의 리스트를 입력받아, 짝수들을 추출하여 리스트로 반환하는 pickup_even 함수 정의

```python
def pickup_even(items):
    a=[]
    for i in itmes:
        if i%2==0:
            a.append(i)
    print(a)
pickup_even([3,4,5,6,7,8])
```
-->

[4,6,8]

5. 주어진 리스트의 평균 구하는 함수

```python
def average(list):
    result=sum(list)/len(list)
    return result

scores= [80, 75, 91, 47, 66, 82, 57, 65, 90, 91, 33, 39, 78, 59, 40, 23, 19, 99, 75, 79, 37, 48, 82, 60, 60, 63, 100, 8, 12, 92, 32, 50, 61, 28, 84, 40, 100, 25, 94, 74, 88, 94, 100, 5, 26]

print(average(scores))
```

*정의 부분을 보고 호출하는 법을 알아야 됨*

*return 값 받는지 안받는지도 중요*

*정의 부분 규격과 호출 부분 규격 맞추기*










 
