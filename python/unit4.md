### list 
list : 하나씩 사용하던 변수를 붙여서 한 줄로 붙여 놓은 개념

- 대괄호 안에 값을 선언
- 한 리스트 안에 다양한 변수의 type이 함께 있을 수 있음 = 문자열, 숫자가 같이 존재할 수 있음
- 리스트 안에 있는 값을 출력할 때는 [] 안에 그 값의 위치를 입력하면 됨 *파이썬은 0부터 시작*

ex. score=[70,80,40,20,10,50] 

print(score) ---> [70,80,40,20,10,50]

print(score[0]) ---> 70 

print(score[-1]) ---> 50  # - 붙이면 뒤에서부터 출력. 맨 뒤는 1부터 시작

print(score[1:4]) ---> [80,40,20]  # [제일 먼저 나올 수 위치 : 마지막에 나올 수 위치+1]

print(score[1:-2]) ---> [80,40,20] 

### 리스트끼리의 덧셈과 곱셈
- 덧셈은 한 리스트에 모든 값을 입력
- 곱셈은 곱하는 수만큼 리스트 값 반복

### 리스트 값 추가
- .append()함수 : 리스트를 먼저 지정해주고 이 리스트 안에 입력값을 넣어줌. 입력한 순서대로 들어

ex. 
```python
x=[]
x.append(1)
x.append(2)
print(x)
```
---> [1,2]

- .insert()함수 : 리스트 값들 사이에 추가할 때 (새로운 값이 들어갈 자리, 새로운 값)

ex.
```python
x=[5,4,3,2,1]
x.insert(2,0)
print(x)
```
---> [5,4,0,3,2,1]

- for문 이용
ex1.
```python
x=[]
for i in range(5):
  x.append(i)
print(x)
```
---> [0,1,2,3,4]

ex2.
```python
x=[0,1,2,3,4]
y=[]
for i in range(5)
  y.append(4-i)  # y.append(x[4-i])
print(y)
```
---> [4,3,2,1,0]

### 리스트 값 변경
바꿀 값의 위치를 지정하고 새롭게 바꿀 값을 입력하면 됨

ex.
```python
a=[1,5,11,-3]
a[0]='hello'
print(a)
```
---> ['hello',5,11,-3]

### 리스트 값 삭제 
- del() : 리스트에서 그 위치에 있는 값을 삭제함 

ex. del(a[0]) = 리스트 a에서 첫번째 값을 삭제함

- [:] = []

ex. a[1:3] = [] = 리스트 a에서 두번째와 세번째 값을 삭제함

- .remove(지울값)함수
    - 중복된 값을 삭제할 때 모든 값을 삭제하지 않고 처음의 한 개만 삭제

ex.
```python
x=[1,4,4,5]
x.remove(4)
print(x)
```
---> [1,4,5]

### 리스트 값 추출
.pop() : 리스트 내 가장 뒤의 값을 뽑아서 삭제

ex.
```python
a=[1,5,11,5,-3]
a.pop()
print(a)
```
---> [1,5,11,5]

### 자주 사용하는 리스트 조작 함수
- .append()
- .insert()
- .remove()
- .pop()
- .sort() : 리스트 안의 값을 오름차순으로 정렬
  - .sort(reverse=True) : 원래 리스트 그대로 출력
- len() : 리스트 안에 있는 값의 갯수를 세줌 
- .count() : 리스트 안에 ()안에 입력한 값(찾을 값)이 몇 개 있는지 세줌
- .copy() : 리스트 복사

### 예제
ex1. greetings 리스트 값 순서대로 출력
```python
greetings=['안녕','니하오','하이','곤니찌와','올라','싸와디캅','봉쥬르']
for i in greetings:   # for i in range(len(greetings)):
  print(i)            #    print(greetings[i])
```

ex2. a 리스트 값 중에서 길이가 5인 값들만 출력
```python
a=['alpha','bravo''charlie','delta','echo','foxtrot','golf','cat','school','hotel','india']
b=[]
for i in a:
  if len(i) == 5:
    b.append(i)
print(b)
```

ex3. 0부터 100까지 수 중에 짝수들 중 큰 수부터 출력
```python
a=[]
b=[]
res=0
for i in range(0,100):
  a.append(res)
  res=res+2
for i in range(0,100):
  b.append(a[99-i])
print(b)
```















