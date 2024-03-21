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



