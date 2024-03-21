### 반복문 (for, while)
반복문을 사용해야 하는 이유 : 수백 줄의 코드를 단 몇 줄로 줄이는 효율 발휘 

주로 조건문과 함께 쓰임

### for문 
- 반복 횟수를 알 때 사용

- for문 형식: for 변수 in range(시작값, 끝값+1, 증가값):

ex. for i in range(0,3,1): --> 0부터 시작해서 2까지 1씩 증가 즉, 숫자면 0,1,2가 출력되고 문자열이면 3개 출력

- 증가값을 생략할 경우 1로 인식함
- 시작값이 0이면 시작값도 생략 가능 (파이썬은 숫자가 0부터 시작)

ex. range(3) = range(0,3,1)

ex1. 1~10까지 숫자들을 차례대로 출력하기
```python
for i in range(1,11,1):
  print(i)
```

ex2. 여러가지 형태의 삼각형 출력하기
```python
for i in range(1,5,1):
  print(i*'*')
```
```python
for i in range(1,5,1):
  print('*'*(5-i))
```
```python
for i in range(1,5):
  print(''*(4-i), '*'*i)
```
빈공간으로 역삼각형을 만들어주는 것
```python
for i in range(1,5):
  print(''*(4-i), '*'*(2*i-1))
```
정삼각형을 출력하기 위해선 빈공간으로 역삼각형을 만들고, 홀수개로 증가해야하기 때문에 2*i-1을 곱해야함

![image](https://github.com/seri-nn/TIL/assets/129299033/278e175e-8ab6-4dcb-bd4c-61e6ec57acef)
![image](https://github.com/seri-nn/TIL/assets/129299033/74201eae-86d9-4150-af73-bbd84475936c)
![image](https://github.com/seri-nn/TIL/assets/129299033/317f26d1-3769-4e27-afbc-e07f238fd2a4)
![image](https://github.com/seri-nn/TIL/assets/129299033/6213f851-782b-4cf9-bfce-e7a94f3c5087)

ex3. 1부터 30까지의 숫자 중 3의 배수만 출력
```python
for i in range(1,30):
  if i%3==0:
    print(i)
```

ex4. 구구단 구하기 
```python
x=int(input("몇단?")
for i in range(1,10,1):
  print("%d x %d = %d" %(x,i,x*i))
```

### for문 활용한 반복적인 덧셈
res : 초기값 설정 

res 변수에 초기값(어떤 값)을 지정해둬야지만 다시 res 변수에 누적해서 새로운 계산이 가능 해짐

ex1. 1000~2000사이에서 홀수의 합을 구하는 프로그램
```python
res=0
for i in range(1000,20001,2):
  res=res+i
print(res)
```
누적해서 합을 구해야하기 때문에 계산하기 쉽도록 초기값을 0으로 잡음

초기 res값은 0이지만 res=res+i 식으로 인해 res 값이 for문을 반복할 때마다 계속 갱신됨

ex2. 팩토리얼 값 구하기
```python
x=int(input("2 이상 숫자 입력:")
res=1
for i in range(1,x+1,1):
  res=res*i
print(res)
```
팩토리얼은 1부터 n까지 차례대로 곱해야하기에 초기값을 0이 아닌 1로 잡음

### 중첩 for문
- for문 안에 또 for문을 사용할 수 있음
- 중첩 for문의 실행 횟수 : 바깥 for문 반복 횟수 x 안쪽 for문 반복 횟수
- 중첩 for문은 중첩된 for문의 j값이 다 끝나고 나서야 첫번째 for문으로 올라옴 (안쪽 for문 먼저 계산 후 바깥쪽 for문 계산)

ex. 구구단 2단부터 9단까지 출력하기 
```python
for i in range(2,10,1):
  for j in range(1,10,1):
    print("%d x %d = %d" %(i,j,i*j))
```

### while문
- while문은 반복 횟수를 결정하기보다는 조건식이 참일 때 반복하는 방식 = 반복 횟수 모를 때 사용
- for문 <-> while문
- i(시작값)와 res(초기값)을 모두 지정해야함
- for문과 달리 i 증가하는 식도 적어야함 -> i가 증가하는 식을 쓰지 않으면 while문이 무한 루프를 하게 됨 (이때는 ctrl + c로 중단)

ex. 1~10까지 모두 더하는 함수
```python
res=0
for i in range(1,11,1):
  res=res+i
print(res)
```
```python
i=1
while i < 11:
  res=res+i
  i=i+1
print(res)
``` 

- break문 : 반복문 안에 break문이 있다면 반복을 중단하고 반복문을 빠져나옴

ex. res값이 40보다 커지면 계산을 멈추고 res값을 출력하기 
```python
i=1
res=0
while i <11:
  res=res+i
  i=i+1
  if res>40:
    break
print(res)
```

- continue문 : 반복문으로 다시 돌아가게 함. 남은 부분을 모두 건너뛰고 반복문의 처음으로 돌아감 = if에 해당하는 값을 패스

ex.
```python
res=0
for i in range(1,11,1):
  if i%3==0:
    continue
  res=res+i
print(res)
``` 
i를 3으로 나눴을 때 마지막이 0이면 continue 즉, 그 값은 패스하고 나머지가 0이 아닐때는 res+i값으로 출력

ex1. 1부터 100까지 숫자를 모두 더한 값을 출력
```python
i=1
res=0
while i<101:
  res=res+i
  i=i+1
print(res)
```

ex2. 1부터 100까지 더하는데 3의 배수는 제외하고 더하기
```python
res=0
i=1
while i<101: 
  if i%3==0:
    i=i+1
    continue
  res=res+i
  i=i+1
print(res)
```
continue 전에도 i값을 증가시켜줘야지만 1,2,3... 차례대로 증가하는 i값을 가질 수 있음 

if문에 들어가지 않고 나온 값에도 i 증가 범위를 써줘야 원하는 계산 가능

if문부터 continue까지를 한 범위로 보고 res=res+i와 i=i+1는 while문에 해당하는 부분이라 생각하면 쉬움

ex3. 복리이자율7%로 1000만원 저금 시 2000만원이 되기까지 몇년이 걸리는가?
```python
year=0
money=1000
while money < 2001:
  money=money*0.07+money
  year=year+1
print(year)
```
이자는 적금 후 1년 뒤부터 붙으니까 초기값은 0이고 처음 적금금액은 1000만원이니까 시작값은 1000

1000만원이 2000만원이 되기까지의 년수를 구하는 거니까 money가 2001보다 작을때까지 반복해야함

1000만원에 0.07프로의 이자값이 더 붙고, 이자가 붙을 때마다 년수가 증가하면 됨

ex4. 30과 75의 최대 공약수 출력
```python
gcm=1
i=1
while i<31:
  if 30%i==0 and 75%i==0:
    gcm=i
  i=i+1
print(gcm)
```
최대공약수 -> 1부터 30까지를 반복하면서 30과 75로 나눴을 때 나머지가 0이면 최대공약수

1은 모든 수의 공약수이기 때문에 초기값을 1로 지정

최대공약수를 구하는거라 반복하는 값이 30보다 클 수는 없음

*gcm=i* gcm값을 i로 받아야함. if문에서 구해진 i는 공약수이고 그 값이 최대공약수가 될 수 있기에 gcm이 i값을 받게함





















